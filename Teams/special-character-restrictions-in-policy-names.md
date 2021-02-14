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
description: 정책 이름에 특수 문자가 있는 문제와 이를 해결하기 위해 할 수 있는 작업을 참조합니다.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814717"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Teams 정책의 특수 문자 제한은 무엇입니까?

Microsoft Teams 관리 센터의 이름에 특수 문자가 있는 정책(메시지, 모임 등)을 만들거나 편집할 **수 없습니다.** 

정책 이름에 특수 문자가 포함되어 있는 경우 Microsoft Teams 관리 센터에서 이러한 정책을 관리하는 데 제한이 있습니다. 따라서 정책 이름에 특수 문자를 **포함하지 않는 것이 좋습니다.** 

Teams에서 모임 및 메시징을 위해 PowerShell을 사용하여 만든 정책 이름은 @,#,$과 같은 특수 문자를 사용할 수 있습니다. 그러나 Microsoft Teams 관리 센터에서 정책을 변경하려는 경우 변경할 수 없습니다. 

특수 문자가 있는 정책이 있는 경우 Windows PowerShell(영원히)를 사용하여 정책을 편집하거나 이전 정책과 동일한 설정으로 Microsoft Teams 관리 센터에서 새 정책을 만들고 동일한 사용자 그룹에 할당해야 합니다.

## <a name="to-remove-special-characters"></a>특수 문자를 제거하려면

**1단계 - PowerShell을 사용하여 원격 연결**
> [!NOTE]
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.
>
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**2단계 - 이전 정책에 대한 설정을 구하고 출력을 캡처합니다.**

> [!NOTE]
> 이 예제는 메시징 [정책에 대한](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 것입니다.  단계는 다른 정책 유형에 대해 동일하지만 올바른 cmdlet을 사용해야 합니다. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**3단계 - 새 정책 만들기**

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 동일한 설정으로 새 정책을 만들 수 있습니다.

이 기능을 실행하면 새 정책이 생성되지만 [Set-CsTeamsMessagingPolicy를](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 확인한 다음 실행하여 올바른 설정을 추가해야 합니다.

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**4단계 - 정책을 할당합니다.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
이 cmdlet에 대한 자세한 내용은 [Grant-CsTeamsMessagingPolicy를](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 참조하세요.

**5단계 - 이전 정책을 삭제합니다.**

이렇게 하면 특수 문자가 있는 이전 정책이 삭제됩니다.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
이 cmdlet에 대한 자세한 내용은 [Remove-CsTeamsMessagingPolicy를](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 참조하세요.

이 명령이 성공하면 완료됩니다. 위의 명령이 오류를 반환하는 경우 이전 정책이 사용자에게 할당되어 정책에서 할당된 모든 사용자를 제거하기 위해 실행해야 했기 때문에 발생합니다.

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자에 대해 설정을 변경할 때도 그렇습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 skype Windows PowerShell 모듈을 사용하면 비즈니스용 Skype Online 및 Microsoft Teams에 Windows PowerShell 원격 Windows PowerShell 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688) Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  

