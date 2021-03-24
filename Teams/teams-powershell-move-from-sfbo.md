---
title: 비즈니스용 Skype Online 커넥터에서 Teams PowerShell 모듈로 이동
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 비즈니스용 Skype Online 커넥터에서 Teams PowerShell 모듈로 이동하여 Teams를 관리하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094129"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>비즈니스용 Skype Online 커넥터에서 Teams PowerShell 모듈로 이동

비즈니스용 Skype Online 커넥터를 Teams PowerShell 모듈로 이동하여 Teams를 관리하려면 기존 PowerShell 스크립트를 업데이트해야 합니다. 이 문서에서는 이 작업을 하는 방법을 설명합니다.

1. 최신 Teams PowerShell 모듈을 설치합니다. 단계에 대한 자세한 내용은 [Microsoft Teams Powershell 설치를 참조하세요.](teams-powershell-install.md)
2. 비즈니스용 Skype Online 커넥터를 제거합니다. 이렇게하려면 제어판에서 프로그램 및 기능으로 **이동하고** 비즈니스용 **Skype Online을** 선택하고 모듈을 Windows PowerShell 선택한 다음 제거를 **선택합니다.** 
3. PowerShell 스크립트에서 에서 또는 로 참조되는 모듈 이름을 ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 변경합니다.

    예를 들어 으로 ```Import-Module -Name SkypeOnlineConnector``` ```Import-Module -Name MicrosoftTeams``` 변경합니다.
4. Teams PowerShell 모듈 2.0 이상을 사용하는 경우 New-csOnlineSession을 Connect-MicrosoftTeams로 변경합니다. 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a>관련 항목

[Microsoft Teams Powershell 설치](teams-powershell-install.md)

[Teams PowerShell을 사용하여 팀 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro?view=skype-ps)