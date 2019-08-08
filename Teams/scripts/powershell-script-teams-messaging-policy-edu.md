---
title: PowerShell 스크립트 샘플-메시징 정책 만들기 및 할당
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트를 사용 하 여 팀에서 메시징 정책을 만들고 조직의 사용자에 게 할당 합니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fd414c960406418e9189a68e219b6a08bb7a939
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243101"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="f3544-103">PowerShell 스크립트 샘플-메시징 정책 만들기 및 할당</span><span class="sxs-lookup"><span data-stu-id="f3544-103">PowerShell script sample - Create and assign a messaging policy</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="f3544-104">이 PowerShell 스크립트를 사용 하 여 Microsoft 팀에서 메시징 정책을 만들고이를 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3544-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="f3544-105">이 PowerShell 스크립트를 사용 하는 방법에 대 한 자세한 내용은 [빠른 시작-교육 팀](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3544-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="f3544-106">PowerShell을 처음 사용 하는 경우 시작 하는 데 도움이 필요한 경우 [Azure PowerShell 개요](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3544-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="f3544-107">예제 스크립트</span><span class="sxs-lookup"><span data-stu-id="f3544-107">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
````


