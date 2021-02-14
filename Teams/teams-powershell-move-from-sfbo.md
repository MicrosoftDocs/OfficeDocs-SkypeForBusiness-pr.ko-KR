---
title: 비즈니스용 Skype Online Connector에서 Teams PowerShell 모듈로 이동
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 비즈니스용 Skype Online Connector에서 Teams PowerShell 모듈로 이동하여 Teams를 관리하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469673"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>비즈니스용 Skype Online Connector에서 Teams PowerShell 모듈로 이동

비즈니스용 Skype Online Connector에서 Teams PowerShell 모듈로 이동하여 Teams를 관리하려면 기존 PowerShell 스크립트를 업데이트해야 합니다. 이 문서에서는 이 작업을 하는 방법을 설명하고 있습니다.

1. 최신 Teams PowerShell 모듈을 설치합니다. 단계는 Microsoft [Teams Powershell 설치를 참조하세요.](teams-powershell-install.md)
2. 비즈니스용 Skype Online Connector를 제거합니다. 이렇게하려면 제어판에서 프로그램 및 기능으로 **이동하여** **비즈니스용 Skype Online,** Windows PowerShell 모듈을 선택한 다음 **제거를 선택합니다.** 
3. PowerShell 스크립트에서 참조되는 모듈 이름을 ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 변경합니다.

    예를 들어 ```Import-Module -Name SkypeOnlineConnector``` . ```Import-Module -Name MicrosoftTeams```

> [!NOTE]
> 관리자는 비즈니스용 Skype Online cmdlet을 사용하기 전에 [New-CsOnlineSession을](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) 계속 사용하고 세션을 가져와야 합니다. 

## <a name="related-topics"></a>관련 항목

[Microsoft Teams Powershell 설치](teams-powershell-install.md)

[Teams PowerShell을 사용하여 Teams 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
