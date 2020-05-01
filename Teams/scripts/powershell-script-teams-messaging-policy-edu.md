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
ms.openlocfilehash: 748167dc8e03b53fc07611df0ff464d984fb5678
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951063"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 스크립트 샘플-메시징 정책 만들기 및 할당

이 PowerShell 스크립트를 사용 하 여 Microsoft 팀에서 메시징 정책을 만들고이를 사용자에 게 할당 합니다. 

이 PowerShell 스크립트를 사용 하는 방법에 대 한 자세한 내용은 [빠른 시작-교육 팀](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)을 참조 하세요.

이 스크립트는 비즈니스용 Skype Online PowerShell 모듈에 있는 [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet을 사용 합니다. PowerShell을 사용 하 여 팀을 관리 하는 방법에 대해 자세히 알아보려면 [팀 PowerShell 개요](../teams-powershell-overview.md) 를 참조 하세요.


## <a name="before-you-start"></a>시작 하기 전에

[비즈니스용 Skype Online PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 다운로드 하 여 설치한 다음 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.

자세히 알아보려면 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)를 참조 하세요.


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

> [!NOTE]
> 일괄 처리 정책 할당을 사용 하 여 대규모 사용자 집합에 메시징 정책을 할당할 수도 있습니다. 자세한 내용은 [학교에서 대규모 사용자 집합에 정책 할당](../batch-policy-assignment-edu.md) 및 [팀에서 사용자에 게 정책 할당](../assign-policies.md)을 참조 하세요.
