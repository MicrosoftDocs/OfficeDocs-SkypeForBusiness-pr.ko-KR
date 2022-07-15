---
title: PowerShell 스크립트 샘플 - 메시징 정책 할당 & 만들기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트를 사용하여 Teams에서 메시징 정책을 만들고 조직의 사용자에게 할당합니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 764de690bbf743991536416c7fed08d0b88e7e97
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825892"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 스크립트 샘플 - 메시징 정책 만들기 및 할당

이 PowerShell 스크립트를 사용하여 Microsoft Teams에서 메시징 정책을 만들고 사용자에게 할당합니다. 

이 PowerShell 스크립트 사용에 대한 자세한 내용은 [빠른 시작 - 교육용 Teams](../teams-quick-start-edu.yml) 참조하세요.

이 스크립트는 비즈니스용 Skype Online PowerShell 모듈에 있는 [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet을 사용합니다. PowerShell을 사용하여 Teams를 관리하는 방법에 대한 자세한 내용은 [Teams PowerShell 개요](../teams-powershell-overview.md) 를 참조하세요.


## <a name="before-you-start"></a>시작하기 전에

[비즈니스용 Skype Online PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=54616)을 다운로드하여 설치한 다음 메시지가 표시되면 컴퓨터를 다시 시작합니다.

자세한 내용은 [Office 365 PowerShell을 사용하여 비즈니스용 Skype Online 관리를 참조하세요](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

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
> 일괄 처리 정책 할당을 통해 대규모 사용자 또는 사용자가 구성원인 그룹에 직접 메시징 정책을 할당할 수도 있습니다. 자세한 내용은 [학교의 대규모 사용자 집합에 정책 할당](../batch-group-policy-assignment-edu.md) 및 [Teams의 사용자에게 정책 할당을 참조하세요](../policy-assignment-overview.md).