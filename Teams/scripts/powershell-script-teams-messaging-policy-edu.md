---
title: PowerShell 스크립트 샘플 - 메시지 & 할당하기
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트를 사용하여 조직에서 메시징 정책을 Teams 조직의 사용자에게 할당합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117276"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 스크립트 샘플 - 메시징 정책 만들기 및 할당

이 PowerShell 스크립트를 사용하여 Microsoft Teams 메시징 정책을 만들고 사용자에게 할당합니다. 

이 PowerShell 스크립트 사용에 대한 자세한 내용은 빠른 시작 - 교육용 Teams [참조하세요.](../teams-quick-start-edu.yml)

이 스크립트는 온라인 PowerShell 모듈에 있는 [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet을 비즈니스용 Skype 사용합니다. PowerSh [Teams ell을 Teams 관리에](../teams-powershell-overview.md) 대한 자세한 내용은 PowerShell 개요를 참조하세요.


## <a name="before-you-start"></a>시작하기 전에

온라인 [PowerShell 비즈니스용 Skype](https://www.microsoft.com/download/details.aspx?id=39366)다운로드하고 설치한 다음 메시지가 표시될 경우 컴퓨터를 다시 시작합니다.

자세한 내용은 [PowerShell을](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)사용하여 비즈니스용 Skype 온라인 Office 365 참조하세요.

## <a name="sample-script"></a>샘플 스크립트

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
> 또한 일괄 처리 정책 할당을 통해 사용자에게 직접 메시징 정책을 할당하거나 사용자가 구성원인 그룹에 할당할 수도 있습니다. 자세한 내용은 [학교의](../batch-group-policy-assignment-edu.md) 대규모 사용자 집합에 정책 할당 및 의 사용자에 정책 [할당을 Teams.](../assign-policies.md)