---
title: 온라인 커넥터에서 비즈니스용 Skype PowerShell 모듈로 Teams 마이그레이션
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 온라인 커넥터에서 비즈니스용 Skype PowerShell 모듈로 Teams PowerShell 모듈로 이동하여 Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd6460e6a17a15193104a0871a57fa6dbff8105
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866360"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>온라인 커넥터에서 비즈니스용 Skype PowerShell 모듈로 Teams 마이그레이션

Teams PowerShell 모듈은 PowerShell 명령줄에서 직접 Teams 관리하기 위한 전체 cmdlet 집합을 제공합니다. 관리자는 비즈니스용 Skype 관리에 대해 비즈니스용 온라인 커넥터를 Teams 없습니다.

> [!NOTE]
> Teams 관리자에게 메시지 센터 게시물(MC244740, 2021년 3월 16일)을 통해 알림을 수신했습니다. 이 변경에 대한 MC250940, 2021년 4월 16일)
>
> Teams PowerShell 모듈은 최신 인증을 사용하지만 기본 인증을 허용하도록 Windows WinRM(원격 관리) 클라이언트를 구성해야 합니다. 기본 [인증을 위해 WinRM을](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) Windows PowerShell 방법에 대한 지침은 다운로드 및 설치를 참조하세요.

## <a name="how-to-migrate"></a>마이그레이션 방법

온라인 커넥터를 비즈니스용 Skype PowerShell 모듈로 Teams 쉽게 마이그레이션할 수 있습니다. 아래 단계에서는 이 작업을 하는 방법을 설명합니다.

1. 최신 PowerShell Teams 설치합니다. 단계에 대한 자세한 내용은 [PowerShell Microsoft Teams 를 참조하세요.](teams-powershell-install.md)

2. 비즈니스용 Skype 커넥터를 제거합니다. 이렇게하려면 제어판에서 프로그램 및 기능으로 **이동하여** 온라인 비즈니스용 Skype, Windows PowerShell 모듈을 선택한 다음 **제거를** **선택합니다.**

3. PowerShell 스크립트에서 참조되는 모듈 이름을 에서 ```Import-Module```

    `SkypeOnlineConnector``LyncOnlineConnector`또는 `MicrosoftTeams` 를 를(를)

    예를 들어 으로 `Import-Module -Name SkypeOnlineConnector` `Import-Module -Name MicrosoftTeams` 변경합니다.

4. PowerShell Teams 2.0 이상을 사용하는 경우 를 참조하는 스크립트를 `New-CsOnlineSession` `Connect-MicrosoftTeams` 업데이트합니다. `Import-PsSession`를 사용할 때 암시적으로 수행되는 비즈니스용 Skype 온라인 원격 PowerShell 세션을 설정하는 데 더 이상 필요하지 `Connect-MicrosoftTeams` 않습니다.

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>관련 항목

[PowerShell Microsoft Teams 설치](teams-powershell-install.md)

[PowerShell을 사용하여 Teams 관리 Teams 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro?view=skype-ps)
