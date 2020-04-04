---
title: PowerShell 스크립트 샘플-메시징 정책 만들기 & 할당
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트를 사용 하 여 팀에서 메시징 정책을 만들고 조직의 사용자에 게 할당 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffd564d421c07503fe5e19ace8f24a0379418b74
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140981"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="58222-103">PowerShell 스크립트 샘플-메시징 정책 만들기 및 할당</span><span class="sxs-lookup"><span data-stu-id="58222-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="58222-104">이 PowerShell 스크립트를 사용 하 여 Microsoft 팀에서 메시징 정책을 만들고이를 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="58222-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="58222-105">이 PowerShell 스크립트를 사용 하는 방법에 대 한 자세한 내용은 [빠른 시작-교육 팀](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58222-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="58222-106">PowerShell을 처음 사용 하는 경우 시작 하는 데 도움이 필요한 경우 [Azure PowerShell 개요](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58222-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="before-you-start"></a><span data-ttu-id="58222-107">시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="58222-107">Before you start</span></span>
<span data-ttu-id="58222-108">[비즈니스용 Skype Online 커넥터 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 다운로드 하 여 설치한 다음 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="58222-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="58222-109">자세한 내용은 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online을 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) 하세요.</span><span class="sxs-lookup"><span data-stu-id="58222-109">View [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) for more.</span></span>


## <a name="sample-script"></a><span data-ttu-id="58222-110">예제 스크립트</span><span class="sxs-lookup"><span data-stu-id="58222-110">Sample script</span></span>

```powershell
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
```


