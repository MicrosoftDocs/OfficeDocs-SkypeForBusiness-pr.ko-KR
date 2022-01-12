---
title: PowerShell 스크립트를 사용하여 정보 장벽 모드 변경
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
description: 정보 장벽을 배포한 후 이 PowerShell 스크립트를 사용하여 테넌트의 모든 그룹에 대해 개방형에서 암시적 모드로 모드를 업데이트합니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3030f40ed61eb2e0e86967132d9575de8334a6c6
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767655"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>PowerShell 스크립트를 사용하여 정보 장벽 모드 변경

이 PowerShell 스크립트를 사용하여 테넌트의 모든 Teams IB(정보 장벽) 모드를 업데이트합니다. 정보 장벽을 배포한 후 이러한 그룹에 대한 모드를 업데이트해야 합니다. IB를 사용하도록 설정하기 전에 프로비전된 그룹은 열기 *모드가 할당됩니다.* *열기* 모드에서는 적용 가능한 IB 정책이 없습니다. IB를 사용하도록  설정하면 암시적이 만드는 모든 새 그룹에 대한 기본 모드가 됩니다. 그러나 기존 그룹은 여전히 *열기 모드 구성을* 유지합니다. 이 스크립트를 실행하여 이러한 기존 그룹을 암시적 모드로 *변경합니다.*

이 스크립트에서는 PowerShell 모듈에 있는 [Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet을 사용하여 Exchange Online 업데이트합니다. PowerShell을 사용하여 Teams 자세한 내용은 [PowerShell Teams 참조하세요.](./teams-powershell-overview.md)

## <a name="sample-script"></a>샘플 스크립트

이 스크립트를 실행하려면 테넌트에 대한 전역 관리자 역할이 할당된 직장 또는 학교 계정을 사용해야 합니다.

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```