---
title: PowerShell 스크립트 샘플-Microsoft 팀 배포 정리 지원
ms.reviewer: ''
author: kenwith
ms.author: kenwith
manager: serdars
audience: admin
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: 이 PowerShell 스크립트를 사용 하 여 대상 컴퓨터 또는 특정 사용자에 대 한 Microsoft 팀을 정리 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.openlocfilehash: f6e6f54bb1e0a4098994f4fb17b167f8ae02dd70
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827586"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>PowerShell 스크립트 샘플-Microsoft 팀 배포 정리
-------------------------------------------------------------------------

이 PowerShell 스크립트는 대상 컴퓨터 또는 사용자 로부터 Microsoft 팀을 정리 하는 데 활용할 수 있습니다. 대상 컴퓨터의 모든 사용자에 대해 실행 되어야 합니다. 


## <a name="sample-script"></a>예제 스크립트

````powershell
<#
.SYNOPSIS
This script allows you to uninstall the Microsoft Teams app and remove Teams directory for a user.
.DESCRIPTION
Use this script to clear the installed Microsoft Teams application. Run this PowerShell script for each user profile for which the Teams App was installed on a machine. After the PowerShell has executed on all user profiles, Teams can be redeployed.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if (Test-Path -Path $TeamsUpdateExePath) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process -FilePath $TeamsUpdateExePath -ArgumentList "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    if (Test-Path -Path $TeamsPath) {
        Write-Host "Deleting Teams directory"
        Remove-Item -Path $TeamsPath -Recurse
                    
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}
````


