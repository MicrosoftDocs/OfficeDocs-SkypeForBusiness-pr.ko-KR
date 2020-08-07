---
title: Microsoft 팀에서 사람 관리자 팀 만들기
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell 스크립트를 사용 하 여 팀 구성원으로 해당 하는 각 관리자의 팀을 만드는 방법에 대해 알아봅니다.
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
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Microsoft 팀에서 사람 관리자 팀 만들기


Microsoft 팀에 "빈 슬레이트" (팀 또는 채널 없음)를 사용 하 여 시작 하지 않고 배포 하는 경우 팀 및 채널의 기본 프레임 워크를 설정 하는 것이 좋습니다. 이렇게 하면 사용자가 기존 팀에서 채널을 만들 때 많은 팀을 만들 수 있는 "팀 sprawl"를 방지할 수 있습니다. 잘 디자인 된 팀과 채널 구조를 시작 하는 데 도움이 되도록 각 관리자의 다이렉트 보고서와 팀 구성원으로 각각의 첫 번째 및 두 번째 줄 사람 관리자를 위한 팀을 만드는 PowerShell 스크립트를 만들었습니다. 이 스크립트는 조직에서 사용자를 추가 하거나 제거할 때 팀 또는 채널이 자동으로 업데이트 되지 않는다는 점에서 "시계열" 스크립트입니다. 그러나 시작부터 팀 구조에 몇 가지 주문을 부과 하는 데 사용할 수 있는 유용한 도구입니다. 이 스크립트는 Azure AD를 읽고 관리자 및 해당 부하 직원의 목록을 가져옵니다. 이 목록을 사용 하 여 사람 관리자 한 명에 게 팀을 만듭니다. 

## <a name="how-to-use-the-powershell-script"></a>PowerShell 스크립트를 사용 하는 방법 

[내보내기 관리자 및 해당](scripts/powershell-script-create-teams-from-managers-export-managers.md) 하는 연결 스크립트 ( [AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) 및 [MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 모듈을 이미 실행 했다고 가정)를 실행 하 여 시작 합니다. *내보내기 관리자 및 해당 하* 는 스크립트는 직속 보고서가 있는 모든 관리자를 나열 하는 탭으로 구분 된 파일 (ExportedManagerDirects.txt)을 만듭니다. 

그런 다음, [새 people manager 팀 만들기 스크립트](scripts/powershell-script-create-teams-from-managers-new-teams.md)를 실행 합니다. 이 스크립트는 ExportedManagerDirects.txt 파일을 읽고 관리자의 직접 보고서를 구성원으로 하 여 각 관리자를 위한 팀을 만듭니다. 팀에 대 한 관리자 또는 다이렉트가 활성화 되지 않은 경우 스크립트는이를 건너뛰고 팀을 만들지 않습니다. (보고서를 검토 한 다음 필요한 모든 사용자에 대해 팀을 켠 후에 스크립트를 다시 실행 합니다. 이 스크립트는 이미 팀을 만든 관리자를 위해 두 번째 팀을 만들지 않습니다.

각 팀에 대해 스크립트는 일반 및 "재미 있는" 채널을 만듭니다. 

## <a name="best-practices"></a>모범 사례

- 각 사용자 관리자에 게 조직의 위기 소통 웹사이트를 각 팀의 일반 채널에 탭으로 추가 해 달라고 요청 합니다. 

- 이 2020 3 월 8 일 블로그 게시물을 읽고 새 위기 소통 앱을 확인 하세요. [Microsoft 팀 + 파워 플랫폼을 사용 하 여 위기 통신을 조정](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)합니다.

## <a name="related-topics"></a>관련 항목

[팀 구성 모범 사례](best-practices-organizing.md)

[Teams에서 조직 전체 팀 만들기](create-an-org-wide-team.md)
