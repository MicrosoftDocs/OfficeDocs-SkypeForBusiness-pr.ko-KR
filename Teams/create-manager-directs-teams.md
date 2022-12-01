---
title: Microsoft Teams에서 사용자 관리자 팀 만들기
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell 스크립트를 사용하여 각 관리자가 팀 구성원으로 직접 팀을 만드는 방법을 알아봅니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89a820a1b828621df2a129b7a972408e7280b3da
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198930"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Microsoft Teams에서 사용자 관리자 팀 만들기


"빈 슬레이트"(팀 또는 채널 없음)로 시작하는 대신 Microsoft Teams를 출시하는 경우 팀과 채널의 기본 프레임워크를 설정하는 것이 좋습니다. 이렇게 하면 사용자가 기존 팀에서 채널을 만들어야 할 때 수많은 팀을 만드는 "팀 스프롤"을 방지하는 데 도움이 됩니다. 잘 디자인된 팀과 채널 구조를 시작할 수 있도록 각 관리자의 직접 보고서를 팀 구성원으로 사용하여 첫 번째 및 두 번째 줄 사용자 관리자 각각에 대한 팀을 만드는 PowerShell 스크립트를 만들었습니다. 이는 "특정 시점" 스크립트입니다(조직에서 사용자가 추가되거나 제거될 때 팀 또는 채널을 자동으로 업데이트하지 않음). 하지만 처음부터 Teams 구조에 주문을 적용하는 데 사용할 수 있는 유용한 도구입니다. 이 스크립트는 Azure AD 읽고 관리자 목록과 직접 보고서를 가져옵니다. 이 목록을 사용하여 사용자 관리자당 하나의 팀을 만듭니다. 

## <a name="how-to-use-the-powershell-script"></a>PowerShell 스크립트를 사용하는 방법 

먼저 [관리자 내보내기 및 해당 지시 스크립트](scripts/powershell-script-create-teams-from-managers-export-managers.md) ( [Connect-AzureAd](/powershell/module/azuread/connect-azuread) 및 [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) PowerShell 모듈을 이미 실행했다고 가정)를 실행합니다. *내보내기 관리자 및 해당 지시* 스크립트는 모든 관리자를 직접 보고서로 나열하는 탭으로 구분된 파일(ExportedManagerDirects.txt)을 만듭니다. 

그런 다음 [새 사용자 관리자 팀 만들기 스크립트](scripts/powershell-script-create-teams-from-managers-new-teams.md)를 실행합니다. 이 스크립트는 ExportedManagerDirects.txt 파일에서 읽고 각 관리자에 대한 팀을 만들고 해당 관리자의 직접 보고서를 구성원으로 만듭니다. Teams에 관리자 또는 직접을 사용할 수 없는 경우 스크립트는 해당 관리자를 건너뛰고 팀을 만들지 않습니다. (보고서를 검토한 다음, 필요한 모든 사용자를 위해 Teams를 켠 후 스크립트를 다시 실행합니다. 스크립트는 이미 팀을 만든 관리자에 대한 두 번째 팀을 만들지 않습니다.

각 팀에 대해 스크립트는 일반 및 "재미를 위해" 채널을 만듭니다. 

## <a name="best-practices"></a>모범 사례

- 각 사용자 관리자에게 조직의 위기 커뮤니케이션 웹 사이트를 각 팀의 일반 채널에 탭으로 추가하도록 요청합니다. 

- 2020년 3월 8일 블로그 게시물: [Microsoft Teams + Power Platform을 사용하여 위기 통신 조정](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)을 참조하여 새로운 위기 통신 앱을 확인하세요.

## <a name="related-topics"></a>관련 주제

[팀 구성 모범 사례](best-practices-organizing.md)

[Teams에서 조직 전체 팀 만들기](create-an-org-wide-team.md)