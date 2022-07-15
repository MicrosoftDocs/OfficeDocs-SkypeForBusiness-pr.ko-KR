---
title: PowerShell 스크립트 샘플 - 새 사용자 관리자 팀 만들기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: brandber
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트를 사용하여 직접 보고서를 팀 구성원으로 사용하여 각 관리자에 대한 팀을 만듭니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b8eb4f60b5bf15e54821181ffedc584d9202669
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825662"
---
# <a name="powershell-script-sample---create-new-people-manager-teams"></a>PowerShell 스크립트 샘플 - 새 사용자 관리자 팀 만들기

이 PowerShell 스크립트를 사용하여 직접 보고서를 팀 구성원으로 사용하여 각 관리자에 대한 팀을 만듭니다. 이 스크립트를 실행하기 전에 [관리자 내보내기](powershell-script-create-teams-from-managers-export-managers.md) 스크립트를 실행하여(Active Directory에서) 관리자 목록과 조직에 대한 직접 보고서를 내보냅니다.

이 PowerShell 스크립트에 대해 알아보려면 [사용자 관리자 팀 만들기](../create-manager-directs-teams.md)를 읽어보세요.

PowerShell을 익숙하지 않은 경우 시작하는 데 도움이 필요한 경우 [Azure PowerShell 개요](/powershell/azure/overview)를 참조하세요.

## <a name="create-new-people-manager-teams"></a>새 사용자 관리자 팀 만들기

```powershell
<#
.SYNOPSIS
  Name: New-TeamsFromManagers.ps1
  This sample script creates a new team for each people manager that includes the manager and their direct reports, based off the ExportedManagerDirects.txt file.

.DESCRIPTION
 This sample script create new Teams based on the tab delimited .txt file you provide of managers and direct reports.

.NOTES
  &copy; 2020 Microsoft Corporation.  All rights reserved.  This document is provided "as-is." Information and views expressed in this document, including URL and other Internet Web site references, may change without notice.

.EXAMPLE
  New-TeamsFromManagers.ps1 -Input .\TeamsToCreate.txt
#>

#region Configurable Inputs
$InputFile = "ExportedManagersDirects.txt"
$ChannelName = "Just for Fun"
#endregion

#region Data Model
class DirectReport {
    [ValidateNotNullOrEmpty()] $UserPrincipalName
    [bool] $TeamsEnabled
}
class Manager {
    [ValidateNotNullOrEmpty()] [string] $UserPrincipalName
    [string] $DisplayName
    [string] $Alias
    [System.Collections.ObjectModel.Collection[DirectReport]]$DirectReports
    [bool] $TeamsEnabled
    [bool] $PassedPrereqs

    Manager (){
        $this.DirectReports = New-Object -TypeName System.Collections.ObjectModel.Collection["DirectReport"]
        $this.PassedPrereqs = $false
    }
}
#endregion

#region Helper Functions
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}
Function IsTeamsEnabled([string] $upn) {
    $user = Get-AzureADUser -ObjectId $upn
    foreach ($plan in $user.AssignedPlans) {
        if (($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") -and ($plan.CapabilityStatus -eq "Enabled")) {
            return $true
        }
    }
    return $false
}
Function ProcessData ($Managers) {
    $output = New-Object -type System.Collections.ObjectModel.Collection["Manager"]

    #Iterate through each manager
    foreach ($manager in $Managers) {
        $boss = New-Object -TypeName Manager
        $boss.UserPrincipalName = $manager.Name
        $boss.DisplayName = $manager.DisplayName
        $boss.TeamsEnabled = IsTeamsEnabled $boss.UserPrincipalName
        $countNonEnabled = 0

        #Iterate over each manager's direct reports
        foreach ($directReport in $manager.Directs) {
            $directs = $manager.Directs.Split(",")
            #Iterate over each direct report
            foreach ($direct in $directs) {
                if ($null -ne $direct) {
                    $person = New-Object -TypeName DirectReport
                    $person.UserPrincipalName = $direct
                    $person.TeamsEnabled = IsTeamsEnabled $person.UserPrincipalName
                    if ($person.TeamsEnabled -eq $false) {
                        $countNonEnabled++
                        Write-Verbose "$(Get-Timestamp) Warning: $($person.UserPrincipalName) is not enabled for Teams."
                    }
                    $boss.DirectReports.Add($person)
                }
            }
        }
        if ($countNonEnabled -eq 0) {
            $boss.PassedPrereqs = $true
        }
        #Add output of Manager/Directs to collection
        $output.Add($boss)
    }
    return $output
}

Function CreateChannel([string] $GroupId, [string] $ChannelDisplayName) {
    if (($null -ne $GroupId) -and ($null -ne $ChannelDisplayName)) {
        New-TeamChannel -GroupId $newTeam.GroupId -DisplayName $ChannelDisplayName | Out-Null
        Write-Verbose "$(Get-Timestamp) Info: Created '$($ChannelDisplayName)' Channel within GroupId($($newTeam.GroupId))."
    }
}

Function AddDirectToTeam([string] $GroupId, [string] $UserPrincipalName) {
    Add-TeamUser -GroupId $newTeam.GroupId -User $direct.UserPrincipalName
    Write-Host "$(Get-Timestamp) Info: Added $($direct.UserPrincipalName) as a Member of GroupId($($newTeam.GroupId))."
}

Function GetNonEnabledTeamsUsers ([manager] $Manager) {
    if ($manager.TeamsEnabled -eq $false) {
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: Manager:$($Manager.UserPrincipalName) not enabled for Teams."
    }
    foreach ($direct in $Manager.DirectReports) {
        if ($direct.TeamsEnabled -eq $false) {
            Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: User:$($direct.UserPrincipalName) not enabled for Teams. Manager:$($Manager.UserPrincipalName)."
        }
    }
}

Function CreateTeam ([manager] $Manager) {
    #Validate both the Manager and Directs are enabled for Teams
    if ($Manager.PassedPrereqs) {
        $alias = $Manager.UserPrincipalName.Split('@')
        $teamName = "$($Manager.DisplayName)'s Team"
        $mailNickName = "$($alias[0])Team"
        if ($Teams.Keys -notcontains $teamName) {
            if ($Teams.Values -notcontains $mailNickName) {
                #Create Team
                $newTeam = New-Team -DisplayName $teamName -MailNickName $mailNickName -Visibility "Private" -Owner $Manager.UserPrincipalName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Created new team for $($Manager.UserPrincipalName) with GroupId: ($($newTeam.GroupId))."

                #Create desired Channel
                CreateChannel $newTeam.GroupId $ChannelName

                if ($null -ne $newTeam) {
                    foreach ($direct in $Manager.DirectReports) {
                        #Add Direct to Team
                        AddDirectToTeam $newTeam.GroupId $direct.UserPrincipalName
                    }
                }
            }
            else {
                    Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: Mailnickname $($mailNickName) already in use. Skipping creating team for $($Manager.UserPrincipalName)."
            }
        }
        else {
            Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: Team already exists for $($Manager.UserPrincipalName). No Team created."
        }
    }
    else {
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: Manager:$($Manager.UserPrincipalName) has the following users not enabled for Teams. No Team created."
        GetNonEnabledTeamsUsers $Manager
    }
}
#endregion

#region Script Execution
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 1: Processing input file."
$Input = import-csv .\"$($InputFile)" -Delimiter `t
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 1: Completed."

Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 2: Processing Team Pre-requisites."
$Managers = ProcessData $Input
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 2: Completed."

Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 3: Creating Teams for each Manager, adding Directs and creating custom Channels."
#This may take awhile, but is needed to ensure Teams are not duplicated.
$AllTeams = Get-Team
$Teams = @{}
if ($null -ne $AllTeams) {
    foreach ($team in $AllTeams) {
        $Teams.Add($team.DisplayName,$team.MailNickName)
    }
}
foreach ($Manager in $Managers) {
    CreateTeam $Manager
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 3: Completed."
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Exiting.."
#endregion
```
