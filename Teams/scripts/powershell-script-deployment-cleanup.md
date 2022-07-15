---
title: PowerShell 스크립트 샘플 - Teams 배포 정리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트를 사용하여 Teams를 제거하고 사용자에 대한 Teams 폴더를 제거합니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7875cb01b928567d5883f36e21eb2f0de0bccf6
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825692"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell 스크립트 샘플 - Teams 배포 정리

이 스크립트를 사용하여 Teams를 제거합니다. 이 스크립트는 Teams를 제거하고 사용자에 대한 Teams 폴더를 제거합니다. Teams가 컴퓨터에 설치된 각 사용자 프로필에 대해 이 스크립트를 실행합니다.


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

## <a name="related-topics"></a>관련 주제

- [Microsoft 엔드포인트 Configuration Manager 사용하여 Microsoft Teams 설치](../msi-deployment.md)
- [Microsoft 365 앱 사용하여 Teams 배포](/deployoffice/teams-install)
