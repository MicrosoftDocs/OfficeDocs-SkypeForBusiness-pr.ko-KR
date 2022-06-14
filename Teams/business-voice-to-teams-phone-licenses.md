---
title: Business Voice에서 Teams 전화 라이선스로 이동
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Business Voice 라이선스를 Teams 전화 라이선스로 변경하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9e973d00761e62e62a3c749163f9e6dcaa8a636
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057098"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>Business Voice에서 Teams 전화 라이선스로 이동

2022년 6월 말까지 Business Voice가 사용 중지되므로 [기업은 Microsoft Teams 전화 및 통화 플랜 패키지 번들 라이선스로 전환하는 것이 좋습니다](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643).

Business Voice는 다음과 같은 세 가지 Teams 추가 기능 라이선스를 번들로 제공했습니다.

- **Microsoft Teams** 클라우드 기반 전화 시스템 대한 Microsoft Teams 전화.
- 모임에 대한 전화 접속 및 전화 접속 회의를 위한 **오디오 회의**.
- PSTN(공중 전화망) 연결에 대한 국내 통화 **요금제** 입니다.

기존 Business Voice 고객은 새 라이선스 모델로 자동으로 전환되지 않습니다.

이 문서는 동일한 기능을 유지하면서 Business Voice 라이선스를 Microsoft Teams 전화 및 오디오 회의 라이선스로 변경해야 하는 IT 관리자를 위한 것입니다.

> [!WARNING]
> 이 문서의 지침을 자세히 따릅니다. 지침에 따라 **저장** 단추를 선택하지 않도록 지시하는 경우 **저장** 단추를 선택하지 마세요.
>
> 조기에 저장하면 전화 번호 할당, 전화 걸기 플랜, 자동 전화 교환 및 통화 큐가 손실 될 수 있습니다.

## <a name="acquire-new-licenses"></a>새 라이선스 획득

Business Voice 라이선스를 교체하기 전에 먼저 사용자를 위한 대체 라이선스를 구매해야 합니다.

이러한 기능을 제공하려면 라이선스가 필요합니다.

- 오디오 회의
- 클라우드 기반 전화 시스템
- PSTN 연결

다음 표를 사용하여 요구 사항에 따라 구매할 라이선스를 결정합니다.

| 이전 라이선스 계획 | 권장 라이선스 계획 | 설명 |
| ---------------- | ------------------------ | ----------- |
| 통화 플랜이 있는 Business Voice | 통화 플랜을 사용하여 Teams 전화 및 미국/CAN으로 전화 접속이 있는 Microsoft Teams 오디오 회의 | 클라우드 기반 전화 시스템 기능, PSTN 공급자로 Microsoft의 국내 통화 플랜, 사용이 허가된 사용자가 구성한 모임 참석자에게 전화 접속 및 전화 접속 기능을 제공합니다. |
| 통화 플랜이 없는 Business Voice | TEAMS 전화 표준 요금제 및 Microsoft Teams 오디오 회의(미국/CAN으로 전화 걸기) | 사용이 허가된 사용자가 구성한 모임 참석자에게 운영자 연결 또는 직접 라우팅 및 전화 접속 및 전화 접속 기능을 [사용하여 PSTN 공급자와 타사 통화 플랜](pstn-connectivity.md)과 결합할 수 있는 클라우드 기반 전화 시스템 기능을 제공합니다. |

## <a name="how-to-update-licenses"></a>라이선스를 업데이트하는 방법

라이선스를 업데이트하는 네 가지 방법이 있습니다.

- Microsoft 365 관리 센터 통한 단일 사용자 라이선스 업데이트
- Microsoft 365 관리 센터 통해 대량 사용자 라이선스 업데이트
- PowerShell 스크립트를 사용하여 대량 사용자 라이선스 업데이트
- Azure 그룹 기반 라이선스를 사용하여 대량 사용자 라이선스 업데이트

# <a name="option-1-single-user-in-admin-center"></a>[옵션 1: 관리 센터의 단일 사용자](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>옵션 1: Microsoft 365 관리 센터 통해 단일 사용자 라이선스 업데이트

단일 사용자를 업데이트하려면 Microsoft 365 관리 센터 사용할 수 있습니다.

1. [admin.microsoft.com](https://admin.microsoft.com/) 이동하여 테넌트 관리자 자격 증명으로 로그인합니다.
1. **사용자****활성 사용자** > 로 이동하고 원하는 사용자를 선택합니다.
1. 목록 도구 모음 **에서 제품 라이선스 관리를** 선택합니다.
1. **라이선스 및 앱** 화면에서 Business Voice 라이선스의 선택을 취소합니다.
    > [!IMPORTANT]
    > 변경 내용을 아직 저장하지 마세요. 새 라이선스를 추가하지 않고 변경 내용을 저장하면 사용자 계정이 프로비전 해제되고 전화 번호가 할당되지 않습니다.
1. Business Voice를 선택 취소한 후 새 Teams 전화 확인하고 라이선스를 오디오 회의.
1. 이제 변경 내용 저장을 선택하여 변경 내용을 안전하게 **저장할** 수 있습니다.

사용자의 라이선스가 업데이트되며 서비스 가용성에 영향을 주지 않아야 합니다.

# <a name="option-2-bulk-users-in-admin-center"></a>[옵션 2: 관리 센터에서 대량 사용자](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>옵션 2: Microsoft 365 관리 센터 통해 대량 사용자 라이선스 업데이트

여러 사용자의 라이선스를 대량으로 업데이트하려면 Microsoft 365 관리 센터 사용할 수 있습니다. 선택한 사용자에게 동일한 라이선스 계획 할당이 있습니다.

1. [admin.microsoft.com](https://admin.microsoft.com/) 이동하여 테넌트 관리자 자격 증명으로 로그인합니다.
1. **사용자****활성 사용자** > 로 이동하고 원하는 모든 사용자를 선택합니다.  
1. 목록 도구 모음 **에서 제품 라이선스 관리를** 선택합니다.
1. **이러한 사용자에 대한 라이선스로 무엇을 하시겠습니까?** 프롬프트에서 **바꾸기: 기존 라이선스 할당 취소 및 새 라이선스 할당** 옵션을 선택합니다.
    > [!IMPORTANT]
    > **바꾸기** 옵션은 선택한 사용자에 대한 모든 기존 라이선스를 제거합니다.  따라서 사용 중인 다른 라이선스(예: Microsoft 365 Business Premium)를 포함하여 사용자에게 원하는 라이선스 상태를 선택해야 합니다.
    >
    > 또한 선택한 사용자에게 다른 기본 라이선스 구성이 있는 경우 선택한 라이선스로 덮어쓰여 다른 Microsoft 365 영역에 영향을 줄 수 있습니다.
    >
    > 혼합 라이선스 설정이 있는 테넌트에는 [PowerShell 스크립트와 함께 대량 업데이트 옵션을](#option-3-bulk-user-license-update-using-a-powershell-script) 사용하는 것이 좋습니다.
1. **라이선스 및 앱** 화면에서 Business Voice 라이선스의 선택을 취소합니다.
    > [!IMPORTANT]
    > 변경 내용을 아직 저장하지 마세요. 새 라이선스를 추가하지 않고 변경 내용을 저장하면 선택한 사용자의 계정이 프로비전 해제되고 전화 번호가 할당되지 않습니다.
1. Business Voice를 선택 취소한 후 새 Teams 전화 확인하고 라이선스를 오디오 회의.
1. 이제 변경 내용 저장을 선택하여 변경 내용을 안전하게 **저장할** 수 있습니다.
  사용자의 라이선스가 업데이트되며 서비스 가용성에 영향을 주지 않아야 합니다.

# <a name="option-3-bulk-users-via-powershell"></a>[옵션 3: PowerShell을 통해 대량 사용자](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>옵션 3: PowerShell 스크립트를 사용하여 대량 사용자 라이선스 업데이트

PowerShell 스크립트를 사용하여 Business Voice 라이선스 계획을 대체하는 것은 대부분의 시나리오에 효율적인 솔루션입니다.  

이 메서드를 사용하려면 다음 일반 단계를 수행합니다.

1. 현재 Business Voice 라이선스의 테넌트별 라이선스 계획 식별자를 가져옵니다.
1. 새 Teams 전화 및 오디오 회의 라이선스 계획의 테넌트별 식별자를 가져옵니다.
1. 새 라이선스 계획에 현재 Business Voice 라이선스와 동일한 서비스 계획이 있는지 확인합니다.
1. Business Voice에 대한 라이선스가 부여된 테넌트 사용자를 찾거나 원하는 경우 필터를 포함하도록 스크립트를 수정하여 사용자 하위 집합을 선택합니다.
1. Teams 전화 및 오디오 회의 계획으로 사용자의 라이선스 구성을 업데이트합니다.

> [!IMPORTANT]
> 제공된 스크립트는 코드 샘플입니다. 스크립트를 있는 그대로 복사하고 특정 환경에 대한 테스트, 유효성 검사 및 사용자 지정 없이 프로덕션 테넌트에서 실행하면 안 됩니다.

### <a name="how-to-bulk-update-licenses-using-powershell"></a>PowerShell을 사용하여 라이선스를 대량 업데이트하는 방법

1. AzureAD PowerShell 모듈을 설치하고 가져옵니다.

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. Microsoft 365 테넌트에 커넥트 테넌트 관리자 자격 증명을 제공합니다.

    ```powershell
    Connect-AzureAD
    ```

1. 다음 commandlet을 사용하여 테넌트에 있는 모든 라이선스 패키지를 나열합니다.

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. 다음 표를 사용하여 대체될 Business Voice 추가 기능 라이선스 계획을 식별합니다.

    | SKU 코드 | 라이선스 유형 |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | 통화 플랜이 있는 Business Voice - 캐나다 |
    | BUSINESS_VOICE | 통화 플랜이 있는 Business Voice - UK |
    | BUSINESS_VOICE_MED2_TELCO | 통화 플랜이 있는 Business Voice - 미국 |
    | BUSINESS_VOICE_DIRECTROUTING | 통화 플랜이 없는 Business Voice |
    | BUSINESS_VOICE_DIRECTROUTING_MED | 통화 플랜이 없는 Business Voice - 미국 |

    > [!NOTE]
    > 이 문서에 제공된 스크립트는 테넌트에 단일 SKU Code for Business Voice가 있다고 가정합니다.  
    >
    > Business Voice SKU가 여러 개 있는 경우 스크립트를 조정하거나 각 SKU 코드에 대해 한 번씩 여러 번 실행해야 합니다.

1. 라는 PowerShell 변수를 만듭니다 `$skuSourceBV`.
    1. 레이블을 `SkuPartNumber` 테넌트의 Business Voice SKU 코드로 바꿔야 합니다.
    1. 이 예제에서는 SKU 코드를 사용합니다 `BUSINESS_VOICE_MED2_TELCO` .

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. 다음 표를 사용하여 새 Teams 전화 및 오디오 회의 라이선스 SKU 코드를 식별합니다.

    | SKU 코드 | 라이선스 유형 |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | 통화 플랜이 포함된 Teams 전화 |
    | MCOEV | Teams 전화 표준 요금제(통화 플랜 없음) |
    | MCOMEETADV | 오디오 회의 |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | Microsoft Teams 오디오 회의 전화 걸기 선택 |

1. 고유한 Teams 전화 저장하고 SKU 코드를 오디오 회의 PowerShell 변수를 만듭니다.
    1. 레이블을 `SkuPartNumber` 테넌트에서 사용할 수 있는 SKU 코드로 바꿔야 합니다.
    1. 이 예제에서는 SKU 코드와 `MCOMEETADV` SKU 코드를 사용합니다`MCOTEAM_ESSENTIALS`.

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. 이 스크립트를 실행하여 원본 SKU에서 고유한 개체로 필요한 서비스 계획 데이터를 수집합니다.

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. 계속 진행하기 전에 원본 SKU(Business Voice)와 대상 SKU(Teams 전화 및 오디오 회의)에 동일한 서비스 계획이 포함되어 있는지 확인합니다.
    1. 불일치는 사용자의 음성 및 오디오 회의 서비스를 방해할 수 있는 라이선스 변경을 트리거할 수 있습니다.
    2. 원본 SKU의 모든 서비스 계획이 동일한 대상 서비스 계획으로 대체될지 유효성을 검사하는 변수를 만듭니다.

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. 원본 Business Voice 라이선스에 통화 플랜이 포함되어 있지 않으면 확인하지 마세요.

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. 원본 SKU의 모든 서비스 계획에 대상 SKU에 일치하는 서비스 계획이 있는지 확인합니다.

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. 대상 SKU에 누락된 서비스 계획이 있는 경우 사용자의 서비스 가용성을 방해할 수 있으며 스크립트 처리를 중지해야 합니다.

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. 모든 항목이 제대로 표시되면 사용자 개체에 대한 업데이트 작업을 수행하도록 PowerShell 개체를 준비합니다. 이 개체를 `AssignedLicenses` 사용합니다.

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. 다음으로, Business Voice 라이선스가 할당된 사용자 목록을 가져와 이름이 지정된 `$usersLicensedOldSKU`목록에 저장합니다.

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. 이제 새 사용자 목록을 사용하여 업데이트 작업을 수행하여 Business Voice 라이선스를 제거하고 이전에 만든 개체를 사용하여 ``$LicensesToUpdate`` Teams 전화 및 오디오 회의 라이선스를 추가합니다.

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> Business Voice를 대체할 수 있는 사용 가능한 Teams 전화 및/또는 오디오 회의 라이선스가 충분하지 않은 경우 라이선스 풀이 고갈되는 즉시 사용자 할당 중에 **SKU guid가 있는 구독에 사용 가능한 라이선스가 없다는** 오류가 발생합니다.

### <a name="full-script"></a>전체 스크립트

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[옵션 4: Azure 그룹 기반 라이선스를 사용하는 대량 사용자](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>옵션 4: Azure 그룹 기반 라이선스를 사용하여 대량 사용자 라이선스 업데이트

Azure 그룹 기반 라이선스 관리를 사용하면 그룹에 구독 및 서비스 계획을 할당할 수 있습니다.

이 메서드는 다음을 보장합니다.

- 라이선스는 그룹의 모든 구성원에게 할당됩니다.
- 그룹에 참가하는 모든 새 구성원에게 적절한 라이선스가 할당됩니다.
- 구성원이 그룹에서 제거되면 해당 라이선스도 제거됩니다.

[그룹 기반 라이선스에 대한 라이선스 요구 사항의 유효성을](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) 검사해야 합니다.

> [!NOTE]
> 이 메서드의 경우 라이선스 업데이트는 한 단계로 처리되어야 합니다.
>
> Business Voice 라이선스가 할당된 기존 그룹 목록을 컴파일하고, 작은 테스트 사용자 그룹을 먼저 선택한 다음, 라이선스 계획 할당을 기본 설정 새 라이선스 계획으로 바꾸는 것이 좋습니다.

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>그룹 기반 라이선스를 사용하여 라이선스를 대량 업데이트하는 방법

1. [portal.azure.com](https://portal.azure.com) 이동하여 관리자 자격 증명으로 로그인합니다.
1. **Azure Active Directory** 이동하고 왼쪽 메뉴에서 **라이선스를** 선택합니다.
1. Business Voice 라이선스가 할당된 그룹을 확인하려면 **모든 제품을** 선택하고 Business Voice 계획을 선택합니다.
1. **사용이 허가된 그룹** 또는 **사용이 허가된 사용자를** 선택합니다. 오른쪽 창에서 사용이 허가된 그룹 목록을 찾을 수 있습니다.
1. 그룹 이름을 선택하여 그룹 할당 세부 정보를 엽니다.
1. **할당을** 선택하여 이 그룹에 할당된 라이선스를 수정합니다.
1. Business Voice를 대체하기 위해 획득한 라이선스 계획 앞에 있는 확인란을 선택합니다.
1. Microsoft 365 Business Voice 라이선스 계획 앞에 있는 확인란을 선택 취소합니다.
1. **저장** 을 선택합니다.
1. 그룹 이름을 선택하여 그룹으로 돌아갑니다. **라이선스 변경이 보류 중이라는 배너가** 표시됩니다.
1. **다시 처리를** 선택하여 라이선스 할당을 강제로 업데이트합니다.

---

## <a name="validate-user-license-updates"></a>사용자 라이선스 업데이트 유효성 검사

선택한 방법을 완료한 후 사용자 라이선스가 제대로 업데이트되었는지 확인합니다.

1. [Microsoft 365 관리 센터](https://admin.microsoft.com) 이동하여 관리자 자격 증명으로 로그인합니다.
1. **사용자****활성 사용자** > 로 이동하고 테스트 사용자를 선택합니다.
1. 도구 모음에서 **제품 라이선스 관리를** 선택합니다.
1. **라이선스 및 앱** 화면에서 할당한 라이선스를 검토합니다.

모든 대상 사용자에게 올바른 라이선스가 할당된 경우 Business Voice 라이선스를 Teams 전화 및 오디오 회의 라이선스로 업데이트하는 작업을 완료했습니다.
