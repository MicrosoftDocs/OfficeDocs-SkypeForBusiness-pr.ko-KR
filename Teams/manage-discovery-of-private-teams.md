---
title: Microsoft 팀에서 비공개 팀의 검색 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 팀 갤러리 및 검색 결과의 제안에 따라 Microsoft 팀 사용자가 개인 팀을 검색할 수 있는지 여부를 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: b60c06299f779ebe798db1ff3df465f1683508ed
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572003"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Microsoft 팀에서 비공개 팀의 검색 관리

[!INCLUDE [preview-feature](includes/preview-feature.md)]

관리자와 팀 소유자는 조직의 Microsoft 팀 사용자가 비공개 팀을 검색할 수 있는지 여부를 제어할 수 있습니다. 개인 팀을 검색할 수 있는 경우에는 검색 결과에 표시 되며 팀의 공용 팀과 함께 팀 갤러리의 제안 사항에 포함 됩니다. 이렇게 하면 사용자가 참여 하려는 비공개 팀을 쉽게 검색 하 고 찾을 수 있습니다. 사용자는 비공개 팀에 참가 하도록 요청할 수 있으며, 팀 소유자는 요청을 승인 하거나 거부할 수 있습니다.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>팀의 공개 팀, 비공개 팀 및 검색 개요

대부분의 조직에는 다음과 같은 종류의 팀 (공개 팀, 검색 가능한 개인 팀, 검색 불가능 한 비공개 팀)이 있습니다.

![팀 갤러리 스크린샷](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>공용 팀

공용 팀은 조직의 모든 사용자가 참가할 수 있습니다. 공용 팀은 팀 갤러리의 모든 사용자가 볼 수 있으며, 사용자는 팀 소유자의 승인을 받을 필요 없이 공용 팀에 참가할 수 있습니다. 공개 팀의 예로는 기술 뉴스, 제품에 대 한 피드백을 얻을 수 있는 팀, 사용자 carpooling 사용할 팀을 토론할 수 있는 팀이 있습니다.

### <a name="discoverable-private-teams"></a>검색 가능한 개인 팀

검색 가능한 비공개 팀은 팀 소유자가 사용자를 추가 하는 경우에만 참가할 수 있습니다. 비공개 팀을 검색할 수 있게 만들면 팀은 팀 갤러리의 추천 팀 및 검색 결과 목록에 포함 됩니다. 모든 사람이 인식 하 고 팀의 대화 및 파일에 대 한 액세스를 제어 해야 하는 조직의 프로젝트 및 그룹에 대해 검색 가능한 개인 팀을 사용 합니다. 예를 들면 HR 부서별로 팀, 조직의 모든 관리자를 위한 팀, 관리자와 팀의 직속 부하 직원 등이 포함 됩니다.

### <a name="non-discoverable-private-teams"></a>검색할 수 없는 비공개 팀

검색할 수 없는 비공개 팀은 팀 소유자가 해당 사용자를 추가 하는 경우에만 참가할 수 있습니다. 개인 팀을 검색할 수 없는 경우 팀 갤러리에서 추천 팀 목록에 표시 되지 않은 상태로 검색 결과에서 제거 됩니다. 검색할 수 없는 팀을 사용 하 여 중요 하 고 기밀 항목을 공동으로 작업 합니다. 예제에는 예정 된 취득 및 팀을 논의 하 여 조직의 전략적 방향에 대 한 변경 내용을 설명 하는 팀이 포함 됩니다.

## <a name="set-whether-new-private-teams-are-discoverable"></a>새 비공개 팀 검색 가능 여부 설정

팀 소유자가 비공개 팀을 만들면 팀의 검색 설정을 구성 하 여 검색 가능 하도록 선택할 수 있습니다. 기본적으로 새 비공개 팀을 검색 하 고 검색할 수 있습니다. 팀 소유자가 개인 팀이 검색 결과 및 제안에 표시 되지 않게 하려는 경우 소유자는이 팀 옆에 있는 **변경 설정을** 선택 하 여 설정을 해제할 수 있으며이는 검색 **및 검색 가능**합니다.

![새 비공개 팀의 검색 설정 스크린샷](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>기존 비공개 팀을 검색할 수 있는지 여부 설정

팀 소유자는 팀 설정에서 직접 기존 개인 팀의 검색 설정을 지정할 수 있으며, 관리자는 PowerShell을 사용 하 여이 작업을 수행할 수 있습니다.

### <a name="in-team-settings"></a>팀 설정

팀에서 비공개 팀으로 이동 하 고 **추가 옵션** > 을 클릭 하 여**팀 관리**를 선택 합니다. **설정** 탭에서 **팀 검색**을 확장 한 다음 검색 **기능 설정** 확인란을 선택 하거나 선택을 취소 합니다.

![기존 비공개 팀의 검색 설정 스크린샷](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a>PowerShell 사용

**[팀](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet을 사용 하 여 기존 개인 팀에 대 한 검색 설정을 끄거나 설정 합니다. 팀을 검색 가능 하 게 만드는 방법의 예는 다음과 같습니다.
```
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
스크립트에서이 cmdlet을 사용 하 여 기존 비공개 팀의 검색 설정을 대량으로 설정할 수 있습니다.

## <a name="set-whether-users-can-discover-private-teams"></a>사용자가 비공개 팀을 검색할 수 있는지 여부 설정

관리자는 조직에서 검색 결과 및 팀의 제안에 따라 비공개 팀을 검색할 수 있는 사용자를 제어할 수도 있습니다. **[CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet을 사용 하 여 정책을 만든 다음 해당 정책을 사용자에 게 할당 합니다.
 
**AllowPrivateTeamDiscovery** 매개 변수를 **true** 로 설정 하 여 정책을 할당 받은 사용자가 검색 결과 및 제안에서 검색 가능한 개인 팀을 볼 수 있도록 합니다. **AllowPrivateTeamDiscovery** 매개 변수를 **false** 로 설정 하면 검색 결과 및 정책에 할당 된 사용자에 대 한 제안에서 모든 검색 가능한 개인 팀이 제거 됩니다.

기본적으로 조직의 모든 사용자에 대해 **AllowPrivateTeamDiscovery** 가 **true** 로 설정 됩니다.

이 예제에서는 사용자가 검색 가능 하도록 설정 된 비공개 팀을 검색 하는 것을 막는 VendorPolicy 라는 정책을 만들고, 정책을 vendoruser1 라는 사용자에 게 할당 합니다.
```
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> 검색할 수 없는 비공개 팀은 정책 설정에 관계 없이 검색 결과 및 제안에 표시 되지 않습니다. 예를 들어 개인 팀에 대 한 검색 설정을 해제 하면 사용자는 해당 사용자에 대 한 정책 설정에서 **AllowPrivateTeamDiscovery** 매개 변수가 **true** 로 설정 된 경우에도 팀을 검색할 수 없습니다.

## <a name="related-topics"></a>관련 항목
- [팀 PowerShell 개요](teams-powershell-overview.md)
