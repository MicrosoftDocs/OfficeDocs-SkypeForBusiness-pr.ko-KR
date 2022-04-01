---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593700"
---
1. PowerShell 버전 7 이상을 설치합니다. 단계별 지침은 [PowerShell](/powershell/scripting/install/installing-powershell-on-windows) 설치를 Windows.

1. 관리자 모드에서 PowerShell을 실행합니다.
1. Microsoft Graph PowerShell 모듈을 설치합니다.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    버전 1.6.1 이상이 있는지 확인 합니다.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. 미리 Teams PowerShell 모듈을 설치합니다.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    적어도 버전 4.1.0이고 Shifts 커넥터 cmdlet이 포함되어 있는지 확인합니다.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. MSAL PowerShell 모듈을 설치합니다.

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. 스크립트를 실행하는 동안 오류가 발생하는 경우 PowerShell을 종료로 설정합니다.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. 스크립트를 실행하여 Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```