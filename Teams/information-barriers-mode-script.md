---
title: PowerShell 스크립트를 사용하여 정보 장벽 모드 변경
description: 테넌트에 있는 모든 그룹에 대해 열려 있는 모드에서 암시적으로 모드를 업데이트하는 정보 장벽을 배포한 후 이 PowerShell 스크립트를 사용합니다.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63403c5e5ee495a7a110aa9239868fd6a9bb5803
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047128"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>PowerShell 스크립트를 사용하여 정보 장벽 모드 변경

이 PowerShell 스크립트를 사용하여 테넌트에 있는 모든 Teams 연결 그룹의 IB(정보 장벽) 모드를 업데이트합니다. 정보 장벽을 배포한 후 이러한 그룹에 대한 모드를 업데이트해야 합니다. IB를 사용하도록 설정하기 전에 프로비전된 그룹에 *는 열기* 모드가 할당됩니다. *오픈* 모드에서는 적용 가능한 IB 정책이 없습니다. IB를 사용하도록 설정하면 만든 새 그룹의 기본 모드가 *암시적* 모드가 됩니다. 그러나 기존 그룹은 여전히 *열기* 모드 구성을 유지합니다. 이 스크립트를 실행하여 이러한 기존 그룹을 *암시적* 모드로 변경합니다.

이 스크립트에서는 Exchange Online PowerShell 모듈에 있는 [Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet을 사용하여 모드를 업데이트합니다. PowerShell을 사용하여 Teams를 관리하는 방법에 대한 자세한 내용은 [Teams PowerShell 개요](./teams-powershell-overview.md)를 참조하세요.

## <a name="sample-script"></a>샘플 스크립트

이 스크립트를 실행하려면 테넌트에 대한 전역 관리자 역할이 할당된 회사 또는 학교 계정을 사용해야 합니다.

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