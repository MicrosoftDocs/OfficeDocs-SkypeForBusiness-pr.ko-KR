---
title: PowerShell 스크립트 샘플 - 관리자 및 직접 보고서 내보내기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: brandber
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트를 사용하여 직접 보고서를 팀 구성원으로 사용하여 각 관리자에 대한 팀을 만들 수 있습니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fbd1758c0de6d0cb7751b4a447e21ab386f823ba
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825672"
---
# <a name="powershell-script-sample---export-managers-and-their-direct-reports"></a>PowerShell 스크립트 샘플 - 관리자 및 직접 보고서 내보내기

이 PowerShell 스크립트를 사용하여 조직의 관리자 목록과 직접 보고서를 내보냅니다. 팀 구성원으로 직접 보고서를 사용하여 각 관리자에 대한 사용자 관리자 팀을 만들기 위한 준비에 이 스크립트를 사용합니다.

이 PowerShell 스크립트에 대해 알아보려면 [사용자 관리자 팀 만들기](../create-manager-directs-teams.md)를 참조하세요.

PowerShell을 익숙하지 않은 경우 시작하는 데 도움이 필요한 경우 [Azure PowerShell 개요](/powershell/azure/overview)를 참조하세요.

## <a name="export-managers-script"></a>Export-Managers 스크립트

```powershell
<#
.SYNOPSIS
  Name: Export-ManagersDirectsFromAAD.ps1
  The purpose of this sample script is to build a list of managers and direct reports to use with the New-TeamsFromManagers.ps1 to create a team for each people manager and their directs.

.DESCRIPTION
 This sample script create new Teams based on the tab delimited .txt file you provide of managers and direct reports. It assumes that DisplayName is not null.

.NOTES
  &copy; 2020 Microsoft Corporation. All rights reserved. This document is provided "as-is." Information and views expressed in this document, including URL and other Internet Web site references, may change without notice.

.EXAMPLE
  Export-ManagersDirectsFromAAD.ps1
#>

#Also create a type that validated the users licenses to ease the create-team burden
#also add checks to see if the types are appropriately in place.

#region Configurable Inputs
$OutputFile = "ExportedManagersDirects.txt"
#endregion

#region Data Model
class DirectReport {
    [string] $UserPrincipalName
}
class Manager {
    [ValidateNotNullOrEmpty()] [string] $UserPrincipalName
    [string] $DisplayName
    [System.Collections.ObjectModel.Collection[DirectReport]]$DirectReports

    Manager (){
        $this.DirectReports = New-Object -TypeName System.Collections.ObjectModel.Collection["DirectReport"]
    }
}
#endregion

#region Helper Functions
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}
#endregion

#region Script Execution
#Step 1: Retrieve AAD users - attribute filtering off DirectReport cannot be applied
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to retrieve ALL Azure AD users."
$AllAADUsers = Get-AzureADUser -All $true -Filter "UserType eq 'Member' and AccountEnabled eq true"
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Azure AD Users Complete.. `n"

#Step 2: Iterate through users, identify Managers and Directs
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to Retrieve Directs Reports"
$Managers = New-Object -TypeName System.Collections.ObjectModel.Collection["Manager"]
foreach ($user in $AllAADUsers) {
    $directs = Get-AzureADUserDirectReport -ObjectId $user.UserPrincipalName
        if ($null -ne $directs) {
            if ($user.DisplayName -ne "") {
                $manager = New-Object -TypeName Manager
                $manager.UserPrincipalName = $user.UserPrincipalName
                $manager.DisplayName = $user.DisplayName

                foreach ($direct in $directs) {
                    $directReport = New-Object -TypeName DirectReport
                    $directReport.UserPrincipalName = $direct.UserPrincipalName
                    $manager.DirectReports.Add($directReport)
                }
                $Managers.Add($manager)

            }
        Write-Host "$(Get-Timestamp) Info: Added Manager: $($manager.UserPrincipalName)"
        $i++
    }
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Direct Reports Complete.. `n"

#Step 3: Output in tab delimited .txt format
$output = New-Object -TypeName System.Collections.ObjectModel.Collection["String"]
$header = "Name`tDisplayName`tDirects"
$output.Add($header)

foreach ($manager in $Managers) {
    [string] $directs = ""
    foreach ($direct in $manager.DirectReports)
    {
        $directs += $direct.UserPrincipalName + ','
    }
    $directs = $directs.Substring(0,$directs.Length-1)
    $row = "$($manager.UserPrincipalName)`t$($manager.DisplayName)`t$($directs)"
    $output.Add($row)
}

#If Output File already exists from a previous run, it will be replaced.
$testPath = Test-Path .\$($OutputFile)
if ($testPath) {
    Remove-Item .\$($OutputFile)
}

foreach ($line in $output) {
    $line | Out-File -FilePath .\$($OutputFile) -Append
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Exported tab delimited output to $($OutputFile). `n"
#endregion
```
