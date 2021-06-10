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
ms.openlocfilehash: 95b7f12f9d7b531de2c50ba2de197f2f799916a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117296"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="29896-103">PowerShell 스크립트 샘플 - Teams 정리</span><span class="sxs-lookup"><span data-stu-id="29896-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="29896-104">이 스크립트를 사용하여 Teams.</span><span class="sxs-lookup"><span data-stu-id="29896-104">Use this script to remove Teams.</span></span> <span data-ttu-id="29896-105">이 스크립트는 사용자에 대한 Teams 제거하고 Teams 폴더를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="29896-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="29896-106">컴퓨터에 설치된 각 사용자 Teams 대해 이 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="29896-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="29896-107">샘플 스크립트</span><span class="sxs-lookup"><span data-stu-id="29896-107">Sample script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="29896-108">관련 항목</span><span class="sxs-lookup"><span data-stu-id="29896-108">Related topics</span></span>

- [<span data-ttu-id="29896-109">Microsoft Teams 사용하여 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="29896-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="29896-110">Teams Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="29896-110">Deploy Teams with Microsoft 365 Apps</span></span>](/deployoffice/teams-install)