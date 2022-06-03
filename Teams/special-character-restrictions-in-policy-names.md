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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: 정책 이름에 특수 문자가 있는 문제 및 문제를 해결하기 위해 수행할 수 있는 작업을 확인합니다.
ms.openlocfilehash: c304e292aa10508e7c8b02fe2825b83897f22e38
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860081"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Teams 정책의 특수 문자 제한은 무엇인가요?

**Microsoft Teams 관리 센터의 이름에 특수 문자가 있는 정책(메시징, 모임 등)을 만들거나 편집할 수 없습니다**. 

정책 이름에 특수 문자가 포함된 경우 Microsoft Teams 관리 센터에서 이러한 정책을 관리할 수 없습니다. **따라서 정책 이름에 특수 문자가 포함되지 않는 것이 좋습니다**. 

Teams 모임 및 메시징에 PowerShell을 사용하여 만든 정책 이름에는 @,#,$와 같은 특수 문자가 있을 수 있습니다. 그러나 Microsoft Teams 관리 센터에서 정책을 변경하려는 경우에는 변경할 수 없습니다. 

특수 문자가 있는 정책이 있는 경우 Windows PowerShell 사용하여 정책을 편집하거나(영원히) 이전 정책과 동일한 설정으로 Microsoft Teams 관리 센터에서 새 정책을 만들고 동일한 사용자 그룹에 할당해야 합니다.

## <a name="to-remove-special-characters"></a>특수 문자를 제거하려면

**1단계 - PowerShell을 사용하여 원격 연결**
> [!NOTE]
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.
>
> 최신 [Teams PowerShell 공개 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/)를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**2단계 - 이전 정책에 대한 설정을 가져와 출력을 캡처합니다.**

> [!NOTE]
> 이 예제는 [메시징](/powershell/module/skype/get-csteamsmessagingpolicy) 정책에 대한 것입니다.  단계는 다른 정책 유형에 대해 동일하지만 올바른 cmdlet을 사용해야 합니다. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**3단계 - 새 정책 만들기**

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 동일한 설정으로 새 정책을 만들 수 있습니다.

이렇게 실행하면 새 정책이 만들어지지만 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy) 를 보고 실행하여 올바른 설정을 추가해야 합니다.

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**4단계 - 정책을 할당합니다.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
이 cmdlet에 대한 자세한 내용은 [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) 를 참조하세요.

**5단계 - 이전 정책을 삭제합니다.**

그러면 특수 문자가 포함된 이전 정책이 삭제됩니다.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
이 cmdlet에 대한 자세한 내용은 [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy) 를 참조하세요.

이 명령이 성공하면 완료됩니다. 위의 명령이 오류를 반환하는 경우 이전 정책이 사용자에게 할당되므로 정책에서 할당된 모든 사용자를 제거하기 위해 실행해야 하기 때문입니다.

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell 사용하여 관리하는 방법을 알고 싶으신가요?

Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.
    
  - [Office 365 PowerShell을 사용해야 하는 이유는 무엇인가요?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Windows PowerShell 사용하여 Microsoft 365 또는 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 한 번에 많은 사용자에 대해 설정을 변경하는 경우와 같이 Microsoft 365 관리 센터 사용하는 것에 비해 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아봅니다.
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Windows PowerShell 사용하여 일반적인 비즈니스용 Skype Online 관리 작업 수행](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > 비즈니스용 Skype Online용 Windows PowerShell 모듈을 사용하면 비즈니스용 Skype Online 및 Microsoft Teams 연결하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype [Online용 Windows PowerShell 모듈](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
