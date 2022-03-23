---
title: 채널 중재 설정 및 관리
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 팀 구성원을 채널 중재자로 추가하는 Microsoft Teams 방법을 포함하여 팀에서 중재를 위해 채널을 설정하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b53a7d71fe7dfde77e9038ef4343539e2375985f
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711322"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>채널에서 채널 중재 설정 및 관리 Microsoft Teams

이 Microsoft Teams 팀 소유자는 표준 채널에 대한 중재를 설정하여 새 게시물을 시작하고 해당 채널의 게시물에 회신할 수 있는 사용자 제어를 할 수 있습니다.

팀 소유자는 팀 구성원을 중재자로 추가할 수 있습니다. 팀 소유자는 채널 중재를 가장 잘 지원하기 위해 채널 수준에서 주제 전문 지식이 없는 것일 수 있습니다. 특정 팀 구성원이 채널을 중재하도록 허용하면 채널 내에서 콘텐츠 및 컨텍스트를 관리하는 책임은 팀 소유자와 채널 중재자 간에 공유됩니다. 예를 들어 팀 소유자는 비즈니스 소유자 또는 콘텐츠 소유자를 중재자로 추가할 수 있습니다. 이를 통해 해당 채널에서 정보 공유를 제어할 수 있습니다.

> [!NOTE]
> 채널 중재는 표준 채널에 사용할 수 있습니다. 일반 채널 또는 개인 또는 공유 채널에는 사용할 수 없습니다.

## <a name="what-can-a-channel-moderator-do"></a>채널 중재자는 무엇을 할 수 있나요?

채널 중재자는 다음을 할 수 있습니다.

- 채널에서 새 게시물을 시작하세요. 채널에 대한 중재가 켜져 있는 경우 중재자만 해당 채널에서 새 게시물을 시작할 수 있습니다.
- 채널에 팀 구성원을 중재자로 추가하고 제거합니다. 기본적으로 팀 소유자는 채널 중재자이며 제거할 수 없습니다.
- 팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부와 봇 및 커넥터가 채널 메시지를 제출할 수 있는지 여부를 제어합니다.

## <a name="scenarios"></a>시나리오

조직에서 채널 중재를 사용하는 방법에 대한 몇 가지 예제는 Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>채널을 공지 채널로 사용

마케팅 팀은 특정 채널을 사용하여 주요 프로젝트 공지사항 및 결과물 공유 팀 구성원이 다른 채널에 더 적절하게 속하는 채널에 콘텐츠를 게시하는 경우도 있습니다. 팀 소유자는 팀 구성원이 해당 채널을 사용하여 중요한 사항을 계속 유지하도록 채널의 정보 공유를 공지로만 제한하려는 것입니다.

이 시나리오에서 팀 소유자는 마케팅 잠재 고객에 중재자로 추가하여 채널에 공지 사항을 게시하고 팀 구성원이 해당 채널의 메시지에 회신할 수 있는 기능을 해제합니다.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>수업 토론을 위해 채널을 교육용 Teams

이 교육용 Teams 교사는 채널을 사용하여 학생들에게 특정 교실 주제에 대한 집중적인 토론에 참여하기를 원합니다.

이 시나리오에서 교사는 교사의 조교가 채널을 중재할 수 있도록 허용합니다. 그런 다음, 조교는 새 게시물을 만들어 학생들과 토론을 시작하고 드라이브할 수 있습니다.

## <a name="manage-channel-moderation"></a>채널 중재 관리

Teams 채널로 이동하여 추가 옵션을 **클릭합니다.** >  **채널을 관리합니다**. 여기에서 중재를 켜고 끄고, 팀 구성원을 중재자로 추가하고, 기본 설정을 설정할 수 있습니다.

채널 중재는 채널당 설정입니다. 채널 중재에 대한 테넌트 수준 설정은 없습니다. 테넌트 수준 채널 중재 설정을 추가하고자 하는 경우 피드백 포털에서 Teams [요청합니다](https://feedbackportal.microsoft.com/feedback/forum/ad198462-1c1c-ec11-b6e7-0022481f8472).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![채널-중재-팀 내 관리에 대한 기본 설정입니다.](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>채널에 대한 중재 켜기 또는 해제

기본적으로 중재가 해제되어 팀 소유자 및 팀 구성원에게 일반적인 채널 설정이 적용됩니다. 예를 들어 팀 구성원만 새 게시물을 제한하거나 게스트를 포함한 모든 사용자가 새 게시물을 시작할 수 있도록 허용할 수 있습니다.

채널에 대한 중재를 켜려면 **채널** 중재에서 켜기 를 **클릭합니다**. 채널 중재가 설정된 경우 중재자만 새 게시물을 시작할 수 있습니다. 

### <a name="add-or-remove-channel-moderators"></a>채널 중재자 추가 또는 제거

중재 **자는 Who 아래** 에서 관리를 클릭한 **다음, 팀** 구성원을 중재자로 추가하거나 제거합니다. 팀 소유자 및 중재자는 다른 중재자 추가 및 제거할 수 있습니다.  

### <a name="set-team-member-permissions"></a>팀 구성원 권한 설정

Team **멤버 권한 아래** 에서 허용할 활동 옆에 있는 확인란을 선택합니다.

## <a name="related-topics"></a>관련 항목

- [Teams의 팀 및 채널 개요](teams-channels-overview.md)
