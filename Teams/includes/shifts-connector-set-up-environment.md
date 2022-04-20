---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976023"
---
1. PowerShell 버전 7 이상을 설치합니다. 단계별 지침은 [Windows PowerShell 설치를](/powershell/scripting/install/installing-powershell-on-windows) 참조하세요.

1. 관리자 모드에서 PowerShell을 실행합니다.
1. Microsoft Graph PowerShell 모듈을 설치합니다.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    버전 1.6.1 이상인지 확인합니다.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Teams Preview PowerShell 모듈을 설치합니다.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    버전 4.1.0 이상이며 Shifts 커넥터 cmdlet이 포함되어 있는지 확인합니다.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. 스크립트를 실행할 때 오류가 발생하면 PowerShell을 종료하도록 설정합니다.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. 스크립트가 Windows 실행되도록 설정합니다.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```