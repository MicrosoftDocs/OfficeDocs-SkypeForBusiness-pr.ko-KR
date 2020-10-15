---
title: 비즈니스용 Skype Online 커넥터에서 팀 PowerShell 모듈로 이동
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 비즈니스용 Skype Online 커넥터에서 팀 PowerShell 모듈로 이동 하 여 팀을 관리 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469673"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>비즈니스용 Skype Online 커넥터에서 팀 PowerShell 모듈로 이동

비즈니스용 Skype Online 커넥터를 팀 PowerShell 모듈로 이동 하 여 팀을 관리 하려면 기존 PowerShell 스크립트를 업데이트 해야 합니다. 이 문서에서는이 작업을 수행 하는 방법을 설명 합니다.

1. 최신 팀 PowerShell 모듈을 설치 합니다. 단계는 [Microsoft 팀 Powershell 설치](teams-powershell-install.md)를 참조 하세요.
2. 비즈니스용 Skype Online Connector를 제거 합니다. 이렇게 하려면 제어판에서 **프로그램 및 기능**으로 이동 하 여 비즈니스용 **Skype Online, Windows PowerShell 모듈**을 선택한 다음 **제거**를 선택 합니다. 
3. PowerShell 스크립트에서 from 또는 to에서 참조 되는 모듈 이름을 변경 ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 합니다.

    예를 들어 ```Import-Module -Name SkypeOnlineConnector``` 로 변경 ```Import-Module -Name MicrosoftTeams``` 합니다.

> [!NOTE]
> 비즈니스용 Skype Online cmdlet을 사용 하기 전에 관리자가 계속 해 서 [CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) 를 사용 하 고 세션을 가져오세요. 

## <a name="related-topics"></a>관련 항목

[Microsoft 팀 Powershell 설치](teams-powershell-install.md)

[팀을 사용 하 여 팀 관리 PowerShell](teams-powershell-managing-teams.md)

[팀 PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
