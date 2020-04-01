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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1dbd4dfa470f8ed02c83e48603dc2647fdc90b3
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096983"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 스크립트 샘플-메시징 정책 만들기 및 할당

이 PowerShell 스크립트를 사용 하 여 Microsoft 팀에서 메시징 정책을 만들고이를 사용자에 게 할당 합니다. 

이 PowerShell 스크립트를 사용 하는 방법에 대 한 자세한 내용은 [빠른 시작-교육 팀](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)을 참조 하세요.

PowerShell을 처음 사용 하는 경우 시작 하는 데 도움이 필요한 경우 [Azure PowerShell 개요](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)를 참조 하세요.


## <a name="before-you-start"></a>시작 하기 전에
[비즈니스용 Skype Online 커넥터 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 다운로드 하 여 설치한 다음 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.

자세한 내용은 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online을 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) 하세요.


## <a name="sample-script"></a>예제 스크립트

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


