---
title: PowerShell 스크립트 샘플-Microsoft 팀 배포 정리 지원
ms.reviewer: ''
author: kenwith
ms.author: kenwith
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: 이 PowerShell 스크립트를 사용 하 여 대상 컴퓨터 또는 특정 사용자에 대 한 Microsoft 팀을 정리 합니다.
localization_priority: Normal
ms.openlocfilehash: f89f35bb34ec3b72cfaec79c651b4c95d5e5bbdd
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "36182210"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="99d1b-103">PowerShell 스크립트 샘플-Microsoft 팀 배포 정리</span><span class="sxs-lookup"><span data-stu-id="99d1b-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="99d1b-104">이 PowerShell 스크립트는 대상 컴퓨터 또는 사용자 로부터 Microsoft 팀을 정리 하는 데 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99d1b-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="99d1b-105">대상 컴퓨터의 모든 사용자에 대해 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99d1b-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="99d1b-106">예제 스크립트</span><span class="sxs-lookup"><span data-stu-id="99d1b-106">Sample script</span></span>

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


