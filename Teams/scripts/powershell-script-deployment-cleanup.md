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
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="7720e-103">PowerShell 스크립트 샘플-팀 배포 정리</span><span class="sxs-lookup"><span data-stu-id="7720e-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="7720e-104">이 스크립트를 사용 하 여 팀을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-104">Use this script to remove Teams.</span></span> <span data-ttu-id="7720e-105">이 스크립트는 팀을 제거 하 고 사용자에 대 한 팀 폴더를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="7720e-106">팀이 컴퓨터에 설치 되어 있는 각 사용자 프로필에 대해이 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="7720e-107">예제 스크립트</span><span class="sxs-lookup"><span data-stu-id="7720e-107">Sample script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="7720e-108">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7720e-108">Related topics</span></span>

- [<span data-ttu-id="7720e-109">Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft 팀 설치</span><span class="sxs-lookup"><span data-stu-id="7720e-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="7720e-110">Microsoft 365 앱을 사용 하 여 팀 배포</span><span class="sxs-lookup"><span data-stu-id="7720e-110">Deploy Teams with Microsoft 365 Apps</span></span>](https://docs.microsoft.com/deployoffice/teams-install)
