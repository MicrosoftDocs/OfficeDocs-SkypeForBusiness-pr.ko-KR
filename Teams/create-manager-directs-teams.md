---
title: 사용자 관리자 팀을 Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell 스크립트를 사용하여 팀 구성원으로 지시를 사용하여 각 관리자에 대한 팀을 만드는 방법에 대해 자세히 알아보습니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cad2ed4fdbcec7f13f5b2e932d34395fe4b4c339
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628360"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>사용자 관리자 팀을 Microsoft Teams


"빈 Microsoft Teams"(팀 또는 채널 없음)을 시작하지 않고 롤아웃할 때 팀 및 채널의 기본 프레임워크를 설정하는 것이 좋습니다. 이렇게 하면 사용자가 기존 팀에서 채널을 만들어야 할 때 사용자가 수많은 팀을 만드는 "팀 스프라우"를 방지하는 데 도움이 됩니다. 잘 디자인된 팀 및 채널 구조를 시작할 수 있도록 각 관리자의 직접 보고서를 팀 구성원으로 사용하여 첫 번째 및 두 번째 줄의 각 관리자에 대한 팀을 만드는 PowerShell 스크립트를 만들어 졌습니다. 이 스크립트는 "지점 시간" 스크립트입니다(조직에서 사용자가 추가되거나 제거될 때 팀 또는 채널을 자동으로 업데이트하지 않습니다). 그러나 이 도구는 시작부터 Teams 순서를 부과하는 데 사용할 수 있는 유용한 도구입니다. 이 스크립트는 Azure AD를 읽고 관리자 목록과 해당 직접 보고서를 제공합니다. 이 목록을 사용하여 사용자 관리자당 하나의 팀을 만들 수 있습니다. 

## <a name="how-to-use-the-powershell-script"></a>PowerShell 스크립트를 사용하는 방법 

먼저 [내보내기](scripts/powershell-script-create-teams-from-managers-export-managers.md) 관리자 및 해당 지시 스크립트를 실행합니다(이미 [커넥트-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) 및 [커넥트-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 모듈을 실행했다고 가정합니다. *내보내기* 관리자 및 해당 지시 스크립트는 모든 관리자를 직접 보고서로 나열하는 탭 ExportedManagerDirects.txt 파일(ExportedManagerDirects.txt)을 만듭니다. 

그런 다음 새 사용자 관리자 [팀 만들기 스크립트 를 실행합니다.](scripts/powershell-script-create-teams-from-managers-new-teams.md) 이 스크립트는 ExportedManagerDirects.txt 각 관리자에 대한 팀을 만들고 해당 관리자의 직접 보고서를 구성원으로 만듭니다. 관리자 또는 직접이 Teams 경우 스크립트가 건너뛰고 팀을 만들지 않습니다. (보고서를 검토한 다음, 필요한 모든 사용자에 대해 Teams 설정한 후 스크립트를 다시 실행합니다. 스크립트는 이미 팀을 만든 관리자에 대해 두 번째 팀을 만들지 않습니다.)

각 팀에 대해 스크립트는 일반 및 "그냥 재미"채널을 만듭니다. 

## <a name="best-practices"></a>모범 사례

- 각 사용자 관리자에게 조직의 위기 통신 웹 사이트를 각 팀의 일반 채널에 탭으로 추가해 보세요. 

- 이 2020년 3월 8일 블로그 게시물: Microsoft Teams + Power Platform을 사용하여 위기 [통신을 조정하여](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)새 위기 통신 앱을 확인하세요.

## <a name="related-topics"></a>관련 주제

[팀 구성에 대한 모범 사례](best-practices-organizing.md)

[Teams에서 조직 전체 팀 만들기](create-an-org-wide-team.md)