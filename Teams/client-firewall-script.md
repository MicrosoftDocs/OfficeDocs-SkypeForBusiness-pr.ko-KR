---
title: 샘플 스크립트 - Microsoft Teams 방화벽 PowerShell 스크립트
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
ms.localizationpriority: medium
search.appverid: MET150
description: Windows 방화벽을 통해 Teams 연결을 허용하도록 Windows를 구성하는 데 사용할 수 있는 샘플 스크립트입니다.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b15c8e141f8a3cd5cde1915901d3dbcd9e29b23a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269403"
---
# <a name="sample-script---microsoft-teams-firewall-powershell-script"></a>샘플 스크립트 - Microsoft Teams 방화벽 PowerShell 스크립트

강화된 관리자 계정 컨텍스트로 클라이언트 컴퓨터에서 실행해야 하는 이 예제 스크립트는 c:\users에 있는 각 사용자 폴더에 새 인바운드 방화벽 규칙을 만듭니다. Teams에서 이 규칙을 찾으면 Teams 응용 프로그램이 사용자가 Teams에서 처음 통화를 할 때 방화벽 규칙을 만들라는 메시지를 표시하지 못하도록 합니다.

```powershell

<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions.
   The script will create a new inbound firewall rule for each user folder found in c:\users.
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
