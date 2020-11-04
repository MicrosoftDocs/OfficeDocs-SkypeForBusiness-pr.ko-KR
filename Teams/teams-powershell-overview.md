---
title: Microsoft 팀 PowerShell 개요
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell 컨트롤을 사용 하 여 Microsoft 팀을 관리 하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852159"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft 팀 PowerShell 개요

Microsoft 팀 PowerShell은 PowerShell 명령줄에서 직접 팀을 관리 하는 cmdlet 집합입니다. .NET Standard로 작성 된 팀 PowerShell은 Azure 클라우드 Shell을 포함 하 여 모든 플랫폼에서 Windows, PowerShell 6.x 이상에서 PowerShell 5.1에서 작동 합니다.

PowerShell 사용을 시작 하려면 먼저 [설치](teams-powershell-install.md)해야 합니다. 

> [!WARNING]
> PowerShell 7 및 팀 PowerShell에 알려진 문제가 있습니다. 문제가 해결 될 때까지 PowerShell 5.1을 사용 하는 것이 좋습니다.

## <a name="releases"></a>릴리스가


두 릴리스 유형의 [Powershell 갤러리](https://www.powershellgallery.com/packages/MicrosoftTeams) 에서 팀 powershell을 사용할 수 있습니다.

- **일반 가용성 (GA)** : 프로덕션에서 사용할 수 있는 cmdlet, 업데이트 된 월간.

- **공개 미리 보기** : 기능에 대 한 조기 액세스입니다. GA 보다 자주 업데이트 될 수 있습니다.

두 릴리스 모두의 기능 추가 및 개선 사항에 대 한 자세한 내용은 [팀 PowerShell 릴리스 정보](teams-powershell-release-notes.md)를 참조 하세요.


## <a name="manage-teams-with-powershell"></a>PowerShell을 사용 하 여 팀 관리

팀 PowerShell 모듈을 사용 하 여 팀을 완벽 하 게 관리 합니다.

- [Microsoft 팀 powershell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/): 팀 powershell 모듈에는 팀, 채팅 및 채널을 관리 하는 cmdlet이 포함 되어 있습니다.

> [!NOTE]
> 최신 [팀 powershell 공개 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/) 는 비즈니스용 Skype Online 커넥터와 통합 되어 팀 PowerShell 관리를 위한 단일 모듈을 제공 합니다.

- 비즈니스용 [Skype Powershell 커넥터](https://www.microsoft.com/download/details.aspx?id=39366): 비즈니스용 skype powershell 커넥터는 이제 팀 powershell 모듈의 일부입니다.

이러한 모듈을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀으로 팀 관리 PowerShell](teams-powershell-managing-teams.md)을 참조 하세요.


## <a name="related-topics"></a>관련 항목

[팀 PowerShell 설치](teams-powershell-install.md)

[팀을 사용 하 여 팀 관리 PowerShell](teams-powershell-managing-teams.md)

[팀 PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Microsoft 팀 관리자 역할을 사용 하 여 팀 관리](using-admin-roles.md)
