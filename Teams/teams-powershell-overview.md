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
description: PowerShell 컨트롤을 사용하여 Microsoft Teams를 관리하는 방법을 학습합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d191d4d1dbb9c3d3d2f206bce76e9d3ddd7d78d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094118"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams PowerShell 개요

Microsoft Teams PowerShell은 PowerShell 명령줄에서 직접 Teams를 관리하기 위한 cmdlet 집합입니다. .NET 표준으로 작성된 Teams PowerShell은 Azure Cloud Shell을 비롯한 모든 플랫폼에서 Windows의 PowerShell 5.1, PowerShell 6.x 이상에서 작동합니다.

PowerShell을 사용하려면 먼저 를 [설치해야 합니다.](teams-powershell-install.md) 

> [!WARNING]
> PowerShell 7 및 Teams PowerShell에 알려진 문제가 있습니다. 문제가 해결될 때까지 PowerShell 5.1을 사용하는 것이 좋습니다.

## <a name="releases"></a>릴리스


Teams PowerShell은 두 가지 릴리스 유형으로 [PowerShell 갤러리에서](https://www.powershellgallery.com/packages/MicrosoftTeams) 사용할 수 있습니다.

- **GA(일반 공급)**: 프로덕션 준비 cmdlet, 월별 업데이트.

- **공개 미리 보기**: 기능에 대한 초기 액세스. GA보다 더 자주 업데이트될 수 있습니다.

두 릴리스에 대한 기능 추가 및 개선에 대한 자세한 내용은 [Teams PowerShell 릴리스 노트 를 참조하세요.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>PowerShell을 사용하여 팀 관리

Teams PowerShell 모듈을 사용하여 Teams를 완전히 관리합니다.

- [Microsoft Teams PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/): Teams PowerShell 모듈에는 팀, 채팅 및 채널을 관리하기 위한 cmdlet이 포함되어 있습니다.

> [!NOTE]
> [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 공개 릴리스 버전 1.1.6 이상은 비즈니스용 Skype Online 커넥터와 통합되어 Teams PowerShell 관리를 위한 단일 모듈을 제공합니다.

- [비즈니스용 Skype PowerShell 커넥터:](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)비즈니스용 Skype PowerShell 커넥터는 이제 Teams PowerShell 모듈의 일부입니다.

이러한 모듈을 사용하여 Teams를 관리하는 전체 가이드는 [Teams PowerShell을 사용하여 Teams 관리를 참조하세요.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>관련 항목

[Teams PowerShell 설치](teams-powershell-install.md)

[Teams PowerShell을 통해 Teams 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro?view=skype-ps)

[Microsoft Teams 관리자 역할을 사용하여 Teams 관리](using-admin-roles.md)