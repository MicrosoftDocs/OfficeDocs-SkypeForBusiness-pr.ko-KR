---
title: PowerShell 스크립트 샘플 - Teams 정리
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트를 사용하여 사용자에 대한 Teams 제거하고 Teams 폴더를 제거합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e542a763127af08344d3d409c5211ff627985124cc191863cf0305e571d55ad5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316834"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell 스크립트 샘플 - Teams 정리

이 스크립트를 사용하여 Teams. 이 스크립트는 사용자에 대한 Teams 제거하고 Teams 폴더를 제거합니다. 컴퓨터에 설치된 각 사용자 Teams 대해 이 스크립트를 실행합니다.


## <a name="sample-script"></a>샘플 스크립트

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

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

- [Microsoft Teams 사용하여 Microsoft Endpoint Configuration Manager](../msi-deployment.md)
- [Teams Microsoft 365 앱](/deployoffice/teams-install)
