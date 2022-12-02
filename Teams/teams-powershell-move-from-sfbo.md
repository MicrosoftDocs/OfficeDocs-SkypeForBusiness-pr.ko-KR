---
title: 비즈니스용 Skype Online 커넥터에서 Teams PowerShell 모듈로 마이그레이션
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 비즈니스용 Skype Online Connector에서 Teams PowerShell 모듈로 이동하여 Teams를 관리하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 648ce1fb69f9e1641840f2e4b92acc1b98f4bbe8
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242292"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>비즈니스용 Skype Online 커넥터에서 Teams PowerShell 모듈로 마이그레이션

Teams PowerShell 모듈은 PowerShell 명령줄에서 직접 Teams를 관리하기 위한 전체 cmdlet 집합을 제공합니다. 관리자는 Teams 관리를 위해 비즈니스용 Skype Online 커넥터를 요구하지 않습니다.

> [!NOTE]
> Teams 관리자는 메시지 센터 게시물(MC244740, 2021년 3월 16일자)을 통해 알림을 받았습니다. MC250940, 2021년 4월 16일자) 이 변경 내용에 대해 알아봅니다.
>
> Teams PowerShell 모듈은 최신 인증을 사용하지만 기본 WinRM(Windows 원격 관리) 클라이언트는 기본 인증을 허용하도록 구성해야 합니다. 기본 인증에 WinRM을 사용하도록 설정하는 방법에 대한 지침은 [Windows PowerShell 다운로드 및 설치](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)를 참조하세요.

## <a name="how-to-migrate"></a>마이그레이션 방법

비즈니스용 Skype Online 커넥터를 사용하여 Teams PowerShell 모듈로 마이그레이션하는 것은 쉽고 간단합니다. 아래 단계에서는 이 작업을 수행하는 방법을 설명합니다.

1. 최신 Teams PowerShell 모듈을 설치합니다. 단계는 [Microsoft Teams PowerShell 설치](teams-powershell-install.md)를 참조하세요.

2. 비즈니스용 Skype Online 커넥터를 제거합니다. 이렇게 하려면 제어판 **프로그램 및 기능** 으로 이동하여 **비즈니스용 Skype Online을 선택하고 모듈을 Windows PowerShell** 제거 **를 선택합니다.**

3. PowerShell 스크립트에서 에서 참조되는 모듈 이름을 변경합니다.```Import-Module```

    `SkypeOnlineConnector` 또는 `LyncOnlineConnector` 를 로 지정합니다 `MicrosoftTeams`.

    예를 들어 를 로 변경 `Import-Module -Name SkypeOnlineConnector` 합니다 `Import-Module -Name MicrosoftTeams`.

4. Teams PowerShell 모듈 2.0 이상을 사용하는 경우 를 참조하는 스크립트를 업데이트합니다 `New-CsOnlineSession` `Connect-MicrosoftTeams`. `Import-PsSession`을 사용할 `Connect-MicrosoftTeams`때 암시적으로 수행되므로 비즈니스용 Skype 온라인 원격 PowerShell 세션을 설정하는 데 더 이상 필요하지 않습니다.

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

## <a name="related-topics"></a>관련 주제

[Microsoft Teams PowerShell 설치](teams-powershell-install.md)

[Teams PowerShell을 사용하여 Teams 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro)
