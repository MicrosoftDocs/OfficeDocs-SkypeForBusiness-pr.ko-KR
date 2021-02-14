---
title: Microsoft Teams에서 사용자 관리자 팀 만들기
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell 스크립트를 사용하여 팀 구성원으로 직접 각 관리자에 대한 팀을 만드는 방법을 배워야 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583677"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Microsoft Teams에서 사용자 관리자 팀 만들기


"빈 슬레이트"(팀 또는 채널 없음)로 시작하지 않고 Microsoft Teams를 출시할 때 팀 및 채널의 기본 프레임워크를 설정하는 것이 좋습니다. 이렇게 하면 사용자가 기존 팀에서 채널을 만들어야 할 때 많은 팀을 만드는 "팀 스플로브"를 방지할 수 있습니다. 잘 디자인된 팀 및 채널 구조를 시작할 수 있도록 각 관리자의 직접 보고서를 팀 구성원으로 사용하여 1줄 및 2줄 사람 관리자 각각에 대한 팀을 만드는 PowerShell 스크립트를 만들 수 있습니다. "시점" 스크립트입니다(조직에서 사용자가 추가되거나 제거될 때 팀 또는 채널이 자동으로 업데이트되지는 않습니다). 하지만 이 도구는 Teams 구조에 순서를 설정하는 데 사용할 수 있는 유용한 도구입니다. 이 스크립트는 Azure AD를 읽고 관리자 및 해당 직접 보고서 목록을 제공합니다. 이 목록을 사용하여 사용자 관리자당 하나의 팀을 만들 수 있습니다. 

## <a name="how-to-use-the-powershell-script"></a>PowerShell 스크립트를 사용하는 방법 

먼저 [내보내기](scripts/powershell-script-create-teams-from-managers-export-managers.md) 관리자 및 해당 직접 스크립트를 실행합니다(Connect-AzureAd 및 [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 모듈을 이미 실행했다고 가정). [](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) 내보내기 관리자 및 해당 *직접* 스크립트는 직접 보고서가 있는 모든 관리자를 나열하는 탭으로 ExportedManagerDirects.txt 파일(ExportedManagerDirects.txt)을 만듭니다. 

그런 다음 새 사용자 관리자 [팀 만들기 스크립트를 실행합니다.](scripts/powershell-script-create-teams-from-managers-new-teams.md) 이 스크립트는 ExportedManagerDirects.txt 파일에서 읽고 해당 관리자의 직접 보고서를 구성원으로 사용하여 각 관리자에 대한 팀을 만듭니다. Teams에 대해 관리자나 직접을 사용하도록 설정하지 않은 경우 스크립트에서 해당 관리자를 건너뛰고 팀을 만들지 않습니다. (보고서를 검토한 다음 필요한 모든 사용자에 대해 Teams를 설정한 후 스크립트를 다시 실행합니다. 스크립트는 이미 팀을 만든 관리자를 위한 두 번째 팀을 만들지 않습니다.)

각 팀에 대해 스크립트는 일반 및 "재미를 위해" 채널을 만듭니다. 

## <a name="best-practices"></a>모범 사례

- 각 팀의 일반 채널에 대한 탭으로 조직의 위기 통신 웹 사이트를 추가해달고 각 사용자 관리자에게 요청합니다. 

- 2020년 3월 8일 블로그 게시물: Microsoft Teams + Power Platform을 사용하여 위기 통신 조정 게시물을 읽어 새로운 Crisis Communications [앱을 확인해 읽습니다.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>관련 항목

[팀 구성 모범 사례](best-practices-organizing.md)

[Teams에서 조직 전체 팀 만들기](create-an-org-wide-team.md)
