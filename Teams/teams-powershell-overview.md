---
title: Microsoft Teams PowerShell 개요
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
description: PowerShell 컨트롤을 사용하여 Microsoft Teams를 관리하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852159"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams PowerShell 개요

Microsoft Teams PowerShell은 PowerShell 명령줄에서 직접 Teams를 관리하기 위한 cmdlet 집합입니다. .NET Standard로 작성된 Teams PowerShell은 Azure Cloud Shell을 포함한 모든 플랫폼에서 Windows의 PowerShell 5.1, PowerShell 6.x 이상에서 작동합니다.

PowerShell 사용을 시작하기 전에 먼저 PowerShell을 [설치해야 합니다.](teams-powershell-install.md) 

> [!WARNING]
> PowerShell 7 및 Teams PowerShell에는 알려진 문제가 있습니다. 문제가 해결될 때까지 PowerShell 5.1을 사용하는 것이 좋습니다.

## <a name="releases"></a>릴리스


Teams PowerShell은 두 가지 릴리스 유형으로 [PowerShell 갤러리에서](https://www.powershellgallery.com/packages/MicrosoftTeams) 사용할 수 있습니다.

- **GA(일반 공급)**: 프로덕션이 준비된 cmdlet, 월별 업데이트

- **공개 미리 보기:** 기능에 대한 초기 액세스입니다. GA보다 더 자주 업데이트될 수 있습니다.

두 릴리스의 기능 추가 및 향상된 기능에 대한 자세한 내용은 [Teams PowerShell 릴리스 정보를 참조하세요.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>PowerShell을 사용하여 Teams 관리

Teams PowerShell 모듈을 사용하여 Teams를 완전히 관리합니다.

- [Microsoft Teams PowerShell 모듈: Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)모듈에는 팀, 채팅 및 채널을 관리하기 위한 cmdlet이 포함되어 있습니다.

> [!NOTE]
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 공개 릴리스는 비즈니스용 Skype Online Connector와 통합되어 Teams PowerShell 관리를 위한 단일 모듈을 제공합니다.

- [비즈니스용 Skype PowerShell 커넥터:](https://www.microsoft.com/download/details.aspx?id=39366)비즈니스용 Skype PowerShell 커넥터는 이제 Teams PowerShell 모듈의 일부입니다.

이러한 모듈을 사용하여 Teams를 관리하는 전체 가이드는 [Teams PowerShell을 사용하여 Teams 관리를 참조하세요.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>관련 항목

[Teams PowerShell 설치](teams-powershell-install.md)

[Teams PowerShell을 통해 Teams 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Microsoft Teams 관리자 역할을 사용하여 Teams 관리](using-admin-roles.md)
