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
ms.openlocfilehash: b8a628ee261ba813b50d58531ab1255a2f121dc4e4719ff4249de70517215cc3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292975"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>정책의 특수 문자 제한은 Teams 무엇입니까?

관리 센터의 이름에 특수 문자가 있는 정책(메시징, 모임 **등)을 만들거나** 편집할 수 Microsoft Teams 없습니다. 

정책 이름에 특수 문자가 포함된 경우 관리 센터에서 이러한 정책을 Microsoft Teams 제한됩니다. **따라서 정책 이름에** 특수 문자가 포함되지 않는 것이 좋습니다. 

PowerShell을 사용하여 만든 정책 이름은 Teams@,#,$과 같은 특수 문자를 사용할 수 있습니다. 그러나 관리 센터에서 정책을 변경하려는 경우 Microsoft Teams 수 없습니다. 

특수 문자가 있는 정책이 있는 경우 이전 정책과 동일한 설정으로 Windows PowerShell(영원)를 사용하여 정책을 편집하거나 Microsoft Teams 관리 센터에서 새 정책을 만들고 동일한 사용자 그룹에 할당해야 합니다.

## <a name="to-remove-special-characters"></a>특수 문자를 제거하려면

**1단계 - PowerShell을 사용하여 원격 연결합니다.**
> [!NOTE]
> 비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.
>
> 최신 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**2단계 - 이전 정책에 대한 설정을 표시하고 출력을 캡처합니다.**

> [!NOTE]
> 이 예제는 메시징 [정책에 대한](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 것입니다.  단계는 다른 정책 유형과 동일하지만 올바른 cmdlet을 사용해야 합니다. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**3단계 - 새 정책 만들기**

관리 센터 또는 PowerShell을 사용하여 동일한 설정으로 새 정책을 Microsoft Teams 수 있습니다.

이 정책을 실행하면 새 정책이 생성되지만 [Set-CsTeamsMessagingPolicy를](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 보고 올바른 설정을 추가한 다음 실행해야 합니다.

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**4단계 - 정책을 할당합니다.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
이 cmdlet에 대한 자세한 내용은 [Grant-CsTeamsMessagingPolicy를](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 참조하세요.

**5단계 - 이전 정책을 삭제합니다.**

이렇게 하면 특수 문자가 있는 이전 정책이 삭제됩니다.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
이 cmdlet에 대한 자세한 내용은 [Remove-CsTeamsMessagingPolicy를](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 참조하세요.

이 명령이 성공하면 완료됩니다. 위의 명령이 오류를 반환하는 경우 이전 정책이 사용자에게 할당되어 있으므로 정책에서 할당된 모든 사용자를 제거하기 위해 실행해야 합니다.

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell을 Office 365 이유는 무엇입니까?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 사용자에 대한 설정을 한 Microsoft 365 관리 센터 설정 변경 시와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 Windows PowerShell 온라인 및 비즈니스용 Skype 원격 세션을 만들 수 Microsoft Teams. 64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
