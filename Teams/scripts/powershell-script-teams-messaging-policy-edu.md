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
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c1df183046dc2378081382e2a8b46c9b3b92c80a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938197"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="56b5e-103">PowerShell 스크립트 샘플-메시징 정책 만들기 및 할당</span><span class="sxs-lookup"><span data-stu-id="56b5e-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="56b5e-104">이 PowerShell 스크립트를 사용 하 여 Microsoft 팀에서 메시징 정책을 만들고이를 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="56b5e-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="56b5e-105">이 PowerShell 스크립트를 사용 하는 방법에 대 한 자세한 내용은 [빠른 시작-교육 팀](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="56b5e-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="56b5e-106">이 스크립트는 비즈니스용 Skype Online PowerShell 모듈에 있는 [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="56b5e-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="56b5e-107">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대해 자세히 알아보려면 [팀 PowerShell 개요](../teams-powershell-overview.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="56b5e-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="56b5e-108">시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="56b5e-108">Before you start</span></span>

<span data-ttu-id="56b5e-109">[비즈니스용 Skype Online PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 다운로드 하 여 설치한 다음 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="56b5e-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="56b5e-110">자세히 알아보려면 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="56b5e-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>


## <a name="sample-script"></a><span data-ttu-id="56b5e-111">예제 스크립트</span><span class="sxs-lookup"><span data-stu-id="56b5e-111">Sample script</span></span>

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

> [!NOTE]
> <span data-ttu-id="56b5e-112">일괄 처리 정책 할당 또는 사용자가 구성원으로 속한 그룹을 통해 확장할 때 사용자에 게 직접 메시징 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56b5e-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="56b5e-113">자세한 내용은 [학교에서 대규모 사용자 집합에 정책 할당](../batch-policy-assignment-edu.md) 및 [팀에서 사용자에 게 정책 할당](../assign-policies.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="56b5e-113">For more information see [Assign policies to large sets of users in your school](../batch-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
