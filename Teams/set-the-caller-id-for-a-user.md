---
title: 사용자의 발신자 ID 설정
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 호출 Microsoft 365 Office 365 기본 호출자 ID(사용자의 할당된 전화 번호)에 대해 자세히 알아보겠습니다. 사용자의 발신자 ID를 변경하거나 차단할 수 있습니다.
ms.openlocfilehash: 9a69cf864cbf57d7ebf82ae079f88a888d3fc9f0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613587"
---
# <a name="set-the-caller-id-for-a-user"></a>사용자의 발신자 ID 설정

전화 시스템 Microsoft 365 사용자의 할당된 전화 번호인 기본 호출자 ID를 제공합니다. 사용자의 발신자 ID(호출 줄 ID라고도 하는)를 변경하거나 차단할 수 있습니다. 조직에서 발신자 ID를 사용할 수 있는 방법 을 확인하여 조직에서 발신자 ID를 사용하는 방법에 대해 [자세히 알아보면 됩니다.](how-can-caller-id-be-used-in-your-organization.md)
  
기본적으로 다음 호출자 ID 설정이 **해제됩니다.** 즉, 해당 사용자가 PSTN Teams 전화를 걸 때 사용자의 전화 번호를 볼 수 있습니다. 다음과 같이 이러한 설정을 변경할 수 있습니다.
  
- **발신 발신자 ID** 기본적으로 해당 전화 번호인 사용자의 발신자 ID를 다른 전화 번호로 바꿀 수 있습니다. 예를 들어 사용자의 발신자 ID를 해당 전화 번호에서 비즈니스의 주 전화 번호로 변경하거나 법률 부서의 주 전화 번호로 변경할 수 있습니다. 또한 전화 ID 번호를 모든 온라인 서비스 번호(전화 또는 무료) 또는 전화 큐 또는 전화 큐에서 사용하는 리소스 계정에 할당된 직접 라우팅을 통해 자동 전화 교환 설정할 수 있습니다.
    
  > [!NOTE]
  > 서비스 매개 변수를 *사용하려면* 유효한 서비스 번호를 지정해야 합니다.
  > 드롭다운에 표시되지 않는 경우 PowerShell New-CsCallingLineIdentity Set-CsCallingLineIdentity PowerShell Teams PowerShell 모듈 2.3.1 이상에서 PowerShell cmdlet을 사용해야 합니다.
  
- **아웃바운드 호출자 ID를 차단합니다.** 사용자의 발신 PSTN 호출에서 발신 호출자 ID가 전송되지 못하도록 차단할 수 있습니다. 이렇게 하면 전화 번호가 호출되는 사람의 휴대폰에 표시되지 않습니다.
    
- **들어오는 발신자 ID를 차단합니다.** 사용자가 들어오는 PSTN 호출에서 발신자 ID를 수신하지 못하도록 차단할 수 있습니다.

- **CNAM(호출 파티 이름)을 설정합니다.** 사용자의 Microsoft Teams 아웃바운드 PSTN 호출에 CNAM을 보낼 수 있습니다.
    
> [!IMPORTANT]
> 긴급 통화는 항상 사용자의 전화 번호(발신자 ID)를 전송합니다. 
  

  
이러한 설정 및 해당 설정을 사용하는 방법에 대한 자세한 내용은 조직에서 발신자 ID를 사용할 수 있는 [방법을 참조하세요.](how-can-caller-id-be-used-in-your-organization.md)
  
## <a name="set-your-caller-id-policy-settings"></a>발신자 ID 정책 설정 설정

> [!NOTE]
> 발신자 ID를 리소스 계정 전화 번호로 설정하고 통화 파티 이름을 설정하려면 PowerShell New-CsCallingLineIdentity 또는 Set-CsCallingLineIdentity PowerShell Teams 2.3.1 이상에서 PowerShell cmdlet을 사용합니다. (이러한 옵션은 현재 관리 센터에서 Microsoft Teams 없습니다.) 

명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>정책 설정 보기, 만들기 및 적용

1. 조직의 모든 호출자 ID 정책 설정을 확인하려면 다음을 실행합니다.

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   자세한 내용은 [Get-CsCallingLineIdentity 를 참조하세요.](/powershell/module/skype/Get-CsCallingLineIdentity)
    
2. 조직에 대한 새 호출자 ID 정책을 만들 경우 New-CsCallingIdentity cmdlet을 사용 합니다.
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    모든 경우 "서비스 번호" 필드에는 초기 "+"가 포함되어 있지 않습니다.

   자세한 내용은 [New-CsCallingLineIdentity 를 참조하세요.](/powershell/module/skype/New-CsCallingLineIdentity)
    
3. Grant-CsCallingIdentity cmdlet을 사용하여 만든 새 정책을 적용합니다. 예를 들어 다음 예제에서는 사용자 Amos Marble에 새 정책을 적용합니다.
    
     ```PowerShell
     Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   자세한 내용은 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet을 참조하세요.
    

4. 들어오는 호출자 ID를 차단하려는 경우 다음을 실행합니다.
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   자세한 내용은 [Set-CsCallingLineIdentity 를 참조하세요.](/powershell/module/skype/Set-CsCallingLineIdentity)
    
5. 조직에서 사용자에게 만든 정책 설정을 적용하기 위해 다음을 실행합니다.
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   자세한 내용은 [Grant-CsCallingLineIdentity 를 참조하세요.](/powershell/module/skype/Grant-CsCallingLineIdentity)

6. 호출자 ID를 지정된 리소스 계정의 전화 번호로 설정하고 호출자 이름을 Contoso로 설정하는 새 호출자 ID 정책을 만들면 다음을 실행합니다.

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

정책을 이미 만든 경우 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
    
### <a name="remove-a-policy-setting"></a>정책 설정 제거

조직에서 정책을 제거하려면 다음을 실행합니다.
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
사용자에서 정책을 제거하려면 다음을 실행합니다.
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 사용하면 관리 Microsoft 365 단순화할 수 있는 단일 관리 지점을 사용하여 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
- [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [를 사용하여 Windows PowerShell 관리하려는 6 가지 Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell 많은 사용자에 대해 설정을 한 Microsoft 365 관리 센터 설정하는 경우와 같이 데이터만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.
    
- [데이터를 사용하여 Microsoft 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>관련 주제
[전화 번호 전송 자주 묻는 질문](./phone-number-calling-plans/port-order-overview.md)

[통화 계획에 사용되는 다양한 종류의 전화 번호](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[전화 회선 ID 및 발신자 이름에 대한 자세한 정보](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)

[비즈니스용 Skype 온라인: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
