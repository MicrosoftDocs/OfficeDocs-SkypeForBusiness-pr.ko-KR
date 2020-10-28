---
title: PowerShell 스크립트 샘플-팀 배포 정리
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트를 사용 하 여 팀을 제거 하 고 사용자 용 팀 폴더를 제거 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7245e3cfee88beb51389f20bc99bbcc312f55b0
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778918"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell 스크립트 샘플-팀 배포 정리

이 스크립트를 사용 하 여 팀을 제거 합니다. 이 스크립트는 팀을 제거 하 고 사용자에 대 한 팀 폴더를 제거 합니다. 팀이 컴퓨터에 설치 되어 있는 각 사용자 프로필에 대해이 스크립트를 실행 합니다.


## <a name="sample-script"></a>예제 스크립트

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````

## <a name="related-topics"></a>관련 항목

- [Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft 팀 설치](../msi-deployment.md)
- [Microsoft 365 앱을 사용 하 여 팀 배포](https://docs.microsoft.com/deployoffice/teams-install)
