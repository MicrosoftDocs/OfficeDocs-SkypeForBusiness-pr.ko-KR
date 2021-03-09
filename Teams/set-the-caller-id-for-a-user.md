---
title: 사용자의 발신자 ID 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 전화선 ID라고도 하는 Microsoft 365 및 Office 365 기본 호출자 ID(사용자의 할당된 전화 번호)에 대해 자세히 알아보겠습니다. 사용자의 발신자 ID를 변경하거나 차단할 수 있습니다.
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569420"
---
# <a name="set-the-caller-id-for-a-user"></a>사용자의 발신자 ID 설정
Microsoft 365 및 Office 365의 전화 시스템은 사용자의 할당된 전화 번호인 기본 호출자 ID를 제공합니다. 사용자의 발신자 ID(호출 줄 ID라고도 하는)를 변경하거나 차단할 수 있습니다. 조직에서 발신자 ID를 사용할 수 있는 방법 을 확인하여 조직에서 발신자 ID를 사용하는 방법에 대해 [자세히 알아보면 됩니다.](how-can-caller-id-be-used-in-your-organization.md)
  
> [!TIP]
> 현재 비즈니스용 Skype Online에서는 들어오는 통화를 차단할 수 없습니다. 
  
변경할 수 있는 설정이 있습니다.
  
> [!NOTE]
> **Lync** 또는 비즈니스용 Skype 서버가 있는 온-프레미스 조직에는 해당되지 않습니다.
  
- **발신자 ID** 변경 기본적으로 해당 전화 번호인 사용자의 발신자 ID를 다른 전화 번호로 바꿀 수 있습니다. 예를 들어 사용자의 발신자 ID를 해당 전화 번호에서 비즈니스의 주 전화 번호로 변경하거나 사용자의 전화 번호에서 법무 부서의 주 전화 번호로 변경할 수 있습니다. 통화 ID 번호를 모든 **온라인** 서비스 번호(전화 또는 무료)로 변경할 수 있습니다.
    
    > [!NOTE]
    > 서비스 매개 변수를  _사용하려면_ 유효한 서비스 번호를 지정해야 합니다.
  
- **아웃바운드 호출자 ID 차단** 사용자의 발신 PSTN 호출에서 발신 호출자 ID가 전송되지 못하도록 차단할 수 있습니다. 이렇게 하면 전화 번호가 호출되는 사람의 휴대폰에 표시되지 않습니다.
    
- **들어오는 발신자 ID 차단** 사용자가 들어오는 PSTN 호출에서 발신자 ID를 수신하지 못하도록 차단할 수 있습니다.
    
> [!IMPORTANT]
> 긴급 통화는 항상 사용자의 전화 번호(발신자 ID)를 전송합니다. 
  
기본적으로 이러한 발신자 ID 설정은 모두 **해제됩니다.** 즉, 해당 사용자가 PSTN 전화로 전화를 걸 때 비즈니스용 Skype Online 사용자의 전화 번호를 볼 수 있습니다.
  
이러한 설정 및 해당 설정을 사용하는 방법에 대한 자세한 내용은 조직에서 발신자 ID를 사용할 수 있는 [방법 을 이동하세요.](how-can-caller-id-be-used-in-your-organization.md)
  
## <a name="set-your-caller-id-policy-settings"></a>발신자 ID 정책 설정 설정

> [!NOTE]
> 비즈니스용 Skype Online의 모든 발신자 ID 설정의 경우 비즈니스용  Skype Windows PowerShell 사용할 **수 없습니다.** 
  
### <a name="start-powershell"></a>PowerShell 시작

- 명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>조직의 모든 발신자 ID 정책 설정 보기

- 조직의 모든 호출자 ID 정책 설정을 확인하려면 다음을 실행합니다.

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  [Get-CsCallingLineIdentity에](https://technet.microsoft.com/library/mt793856.aspx)대한 자세한 예제 및 세부 정보를 참조합니다.
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>조직에 대한 새 발신자 ID 정책 만들기


- 호출자 ID를 익명으로 설정하는 새 호출자 ID 정책을 만들 경우 다음을 실행합니다.
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > 모든 경우 "서비스 번호" 필드에는 초기 "+"가 포함되어 있지 않습니다.

  [New-CsCallingLineIdentity에](https://technet.microsoft.com/library/mt793855.aspx)대한 자세한 예제 및 세부 정보를 참조합니다.
    
- Amos Marble에 만든 새 정책을 적용하기 위해 다음을 실행합니다.
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet을 참조합니다.
    
정책을 이미 만든 경우 [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>들어오는 발신자 ID가 차단되지 있도록 설정

- 들어오는 호출자 ID를 차단하기 위해 다음을 실행합니다.
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  [Set-CsCallingLineIdentity에](https://technet.microsoft.com/library/mt793854.aspx)대한 자세한 예제 및 세부 정보를 참조합니다.
    
- 조직에서 사용자에게 만든 정책 설정을 적용하기 위해 다음을 실행합니다.
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet을 참조합니다.
    
### <a name="remove-a-caller-id-policy"></a>호출자 ID 정책 제거

조직에서 정책을 제거하려면 다음을 실행합니다.
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
사용자에서 정책을 제거하려면 다음을 실행합니다.
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 또는 Office 365를 Windows PowerShell 사용하려는 6 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [비즈니스용 skype Windows PowerShell 관리하기 위해 사용](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](/microsoftteams/transferring-phone-numbers-common-questions)

[통화 계획에 사용되는 다양한 종류의 전화 번호](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[전화 회선 ID 및 발신자 이름에 대한 자세한 정보](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)

[비즈니스용 Skype Online: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
