---
title: Teams 정책의 특수 문자 제한 사항
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: 정책 이름에 특수 문자와 문제 해결을 위해 수행할 수 있는 작업에 대해 알아봅니다.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814717"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>팀 정책의 특수 문자 제한 사항은 무엇 인가요?

**Microsoft 팀 관리 센터에서 이름에 특수 문자를 포함 하는 정책을 만들거나 편집할 수 없습니다 (메시징, 모임 등)**. 

정책 이름에 특수 문자가 포함 된 경우 Microsoft 팀 관리 센터에서 이러한 정책 관리에 제한을 받습니다. 따라서 **정책 이름에 특수 문자를 포함 하지 않는 것이 좋습니다**. 

팀에서 모임 및 메시지에 대해 PowerShell을 사용 하 여 만든 정책 이름은 @, #, $와 같은 특수 문자를 포함할 수 있습니다. 그러나 Microsoft 팀 관리 센터에서 정책을 변경 하려는 경우에는이 작업을 수행할 수 없습니다. 

특수 문자를 사용 하는 정책이 있는 경우 Windows PowerShell을 사용 하 여 정책 편집 (계속) 하거나 기존 정책과 동일한 설정을 사용 하 여 Microsoft 팀 관리 센터에서 새 정책을 만든 다음 동일한 사용자 그룹에 할당 해야 합니다.

## <a name="to-remove-special-characters"></a>특수 문자를 제거 하려면

**1 단계-PowerShell을 사용 하 여 원격 연결을 설정 합니다.**
> [!NOTE]
> 비즈니스용 Skype Online 커넥터는 현재 최신 팀 PowerShell 모듈의 일부입니다.
>
> 최신 [팀 PowerShell 공용 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/)를 사용 하 고 있는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**2 단계-이전 정책에 대 한 설정을 가져오고 출력을 캡처합니다.**

> [!NOTE]
> 이 예제는 [메시징](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 정책에 대 한 것입니다.  단계는 다른 정책 유형의 경우와 동일 하지만 올바른 cmdlet을 사용 해야 합니다. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**3 단계-새 정책 만들기**

Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 동일한 설정으로 새 정책을 만들 수 있습니다.

이 작업을 실행 하면 새 정책이 만들어지지만, [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 를 표시 한 다음 실행 하 여 올바른 설정을 추가 해야 합니다.

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**4 단계-정책을 할당 합니다.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
이 cmdlet에 대 한 자세한 내용은 [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 을 참조 하세요.

**5 단계-이전 정책 삭제**

이렇게 하면 특수 문자를 사용 하 여 이전 정책이 삭제 됩니다.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
이 cmdlet에 대 한 자세한 내용은 [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 를 참조 하세요.

이 명령이 성공 하면 완료 됩니다. 위의 명령에서 오류를 반환 하는 경우 정책에서 할당 된 모든 사용자를 제거 하기 위해 이전 정책이 사용자에 게 할당 되므로이는 실행 되어야 합니다.

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유는 무엇 인가요?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online 및 Microsoft 팀에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  

