---
title: 사용자의 발신자 ID 설정
ms.author: tonysmit
author: tonysmit
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
description: 전화 라인 ID 라고도 하는 Office 365 기본 발신자 ID (사용자의 지정 된 전화 번호)에 대해 알아봅니다. 사용자의 발신자 ID를 변경 하거나 차단할 수 있습니다.
ms.openlocfilehash: c04fdfa7dc395f31eb3277fe0ab2f77aa92605c7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140911"
---
# <a name="set-the-caller-id-for-a-user"></a>사용자의 발신자 ID 설정
Office 365의 전화 시스템은 사용자가 할당 한 전화 번호에 해당 하는 기본 발신자 ID를 제공 합니다. 사용자의 발신자 ID (통화 라인 ID 라고도 함)를 변경 하거나 차단할 수 있습니다. 조직에서 발신자 id를 사용 하는 [방법을](how-can-caller-id-be-used-in-your-organization.md)확인 하 여 조직에서 발신자 id를 사용 하는 방법에 대해 자세히 알아볼 수 있습니다.
  
> [!TIP]
> 현재 비즈니스용 Skype Online에서 수신 전화를 차단할 수 없습니다. 
  
변경할 수 있는 설정은 다음과 같습니다.
  
> [!NOTE]
> 이 **는** Lync 또는 비즈니스용 Skype Server를 사용 하는 온-프레미스 조직에는 해당 되지 않습니다.
  
- **보내는 발신자 ID 변경** 기본적으로 사용자의 발신자 ID를 다른 전화 번호로 바꿀 수 있습니다. 예를 들어 사용자의 발신자 ID를 자신의 전화 번호에서 비즈니스의 기본 전화 번호로 변경 하거나 사용자의 통화 라인 ID를 자신의 전화 번호에서 법률 부서의 대표 전화 번호로 변경할 수 있습니다. 전화 번호를 온라인 **서비스** 번호로 변경 (유료 또는 무료 무료) 할 수 있습니다.
    
    > [!NOTE]
    > _서비스_ 매개 변수를 사용 하려면 유효한 서비스 번호를 지정 해야 합니다.
  
- **아웃 바운드 발신자 ID 차단** 사용자의 발신 PSTN 호출에서 보내는 발신자 ID를 보내는 것을 차단할 수 있습니다. 이렇게 하면 전화 번호가 호출 되는 사람의 전화에 표시 되지 않습니다.
    
- **받는 발신자 ID 차단** 사용자가 들어오는 PSTN 호출에 대해 발신자 ID를 받지 못하도록 차단할 수 있습니다.
    
> [!IMPORTANT]
> 비상 전화는 항상 사용자의 전화 번호 (발신자 ID)를 보냅니다. 
  
기본적으로 이러한 모든 발신자 ID 설정이 **해제**됩니다. 이는 사용자가 PSTN 전화기로 전화를 걸 때 비즈니스용 Skype Online 사용자의 전화 번호가 표시 될 수 있음을 의미 합니다.
  
이러한 설정과 이러한 설정을 사용 하는 방법에 대 한 자세한 내용은 [조직에서 발신자 ID를 사용](how-can-caller-id-be-used-in-your-organization.md)하는 방법을 참고 하세요.
  
## <a name="set-your-caller-id-policy-settings"></a>발신자 ID 정책 설정

> [!NOTE]
> 비즈니스용 Skype Online의 모든 발신자 ID 설정에 대해 Windows PowerShell을 사용 해야 하며 **비즈니스용 skype 관리 센터**를 **사용할 수 없습니다** . 
  
### <a name="verify-and-start-windows-powershell"></a>Windows PowerShell 확인 및 시작

- **Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**
    
1. 버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.
    
2. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.
    
3. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
4. 비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
    자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.
    
- **Windows PowerShell 세션 시작**
    
1. **시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.
    
2. **Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.
    
   > [!NOTE]
   > 비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요.
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>조직의 모든 발신자 ID 정책 설정 보기

- 조직의 모든 발신자 ID 정책 설정을 보려면 다음을 실행 합니다.

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx)에 대 한 추가 예제 및 세부 정보를 확인 하세요.
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>조직에 대 한 새 발신자 ID 정책 만들기


- 발신자 ID를 익명으로 설정 하는 새 발신자 ID 정책을 만들려면 다음을 실행 합니다.
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > 모든 경우에 "서비스 번호" 필드에는 초기 "+"가 포함 되어서는 안 됩니다.

  [새로운 CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx)에 대 한 추가 예제 및 세부 정보를 확인 하세요.
    
- 만든 새 정책을 Amos 대리석에 적용 하려면 다음을 실행 합니다.
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.
    
이미 정책을 만든 경우 [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음 [부여-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet을 사용 하 여 사용자에 게 설정을 적용할 수 있습니다.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>들어오는 발신자 ID가 차단 되도록 설정

- 들어오는 발신자 ID를 차단 하려면 다음을 실행 합니다.
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx)에 대 한 추가 예제 및 세부 정보를 확인 하세요.
    
- 조직의 사용자에 게 만든 정책 설정을 적용 하려면 다음을 실행 합니다.
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.
    
### <a name="remove-a-caller-id-policy"></a>발신자 ID 정책 제거

조직에서 정책을 제거 하려면 다음을 실행 합니다.
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
사용자에서 정책을 제거 하려면 다음을 실행 합니다.
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 데 필요한 여섯 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](/microsoftteams/transferring-phone-numbers-common-questions)

[통화 요금제에 사용 되는 다른 종류의 전화 번호](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[전화 회선 ID 및 발신자 이름에 대한 자세한 정보](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)

[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
