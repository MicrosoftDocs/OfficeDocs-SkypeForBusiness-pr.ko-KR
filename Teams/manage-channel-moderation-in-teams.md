---
title: 채널 중재 설정 및 관리
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: 팀 구성원을 채널 중재자로 추가하는 방법을 포함하여 Microsoft Teams에서 중재를 위한 채널을 설정하는 방법을 배워 보세요.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9598723d1a88826d1efa5fb487d02fc93aa5d4e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822898"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Microsoft Teams에서 채널 중재 설정 및 관리

Microsoft Teams에서 팀 소유자는 표준 채널에 대한 중재를 설정하여 해당 채널에서 새 게시물을 시작하고 게시물에 회신할 수 있는 사용자 제어를 할 수 있습니다.

팀 소유자는 팀 구성원을 중재자로 추가할 수 있습니다. 팀 소유자는 채널 중재를 가장 잘 지원하기 위해 채널 수준에서 주제에 대한 전문 지식이 없는 것일 수 있습니다. 특정 팀 구성원이 채널을 중재하도록 허용하면 채널 내에서 콘텐츠 및 컨텍스트를 관리하는 책임이 팀 소유자와 채널 중재자 간에 공유됩니다. 예를 들어 팀 소유자는 비즈니스 소유자 또는 콘텐츠 소유자를 중재자로 추가하여 해당 채널에서 정보 공유를 제어할 수 있습니다.

> [!NOTE]
> 채널 중재는 표준 채널에 사용할 수 있습니다. 일반 채널 또는 비공개 채널에는 사용할 수 없습니다.

## <a name="what-can-a-channel-moderator-do"></a>채널 중재자는 무엇을 할 수 있나요?

채널 중재자는 다음을 할 수 있습니다.

- 채널에서 새 게시물을 시작하세요. 채널에 대한 중재가 설정되어 있는 경우 중재자만 해당 채널에서 새 게시물을 시작할 수 있습니다.
- 채널에 중재자로 팀 구성원을 추가하고 제거합니다. 기본적으로 팀 소유자는 채널 중재자로, 제거할 수 없습니다.
- 팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부와 봇과 커넥터가 채널 메시지를 제출할 수 있는지 여부를 제어합니다.

## <a name="scenarios"></a>시나리오

다음은 조직에서 Teams에서 채널 중재를 사용하는 방법에 대한 몇 가지 예입니다.

### <a name="use-a-channel-as-an-announcement-channel"></a>채널을 공지 채널로 사용

마케팅 팀은 특정 채널을 사용하여 주요 프로젝트 공지 및 결과물 공유 경우에 따라 팀 구성원은 다른 채널에 더 적절하게 속하는 채널에 콘텐츠를 게시합니다. 팀 소유자는 팀 구성원이 해당 채널을 사용하여 중요한 사항을 계속 볼 수 있도록 채널의 정보 공유를 공지로만 제한하기를 원합니다.

이 시나리오에서 팀 소유자는 마케팅 리드를 중재자로 추가하여 채널에 공지 사항을 게시하고 팀 구성원이 해당 채널의 메시지에 회신할 수 있는 기능을 해제합니다.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>교육용 Teams에서 수업 토론을 위한 채널 사용

교육용 Teams에서 과학 교사는 채널을 사용하여 학생에게 특정 교실 주제에 대한 집중적인 토론에 참여하기를 원합니다.

이 시나리오에서 교사는 교육 도우미가 채널을 중재할 수 있도록 허용합니다. 그런 다음, 교육 도우미는 새 게시물을 만들어 학생들과 토론을 시작하고 진행할 수 있습니다.

## <a name="manage-channel-moderation"></a>채널 중재 관리

Teams에서 채널로 이동하고 추가 **옵션을 클릭합니다.**  >  **채널을 관리합니다.** 여기에서 중재를 설정 및 해제하고, 팀 구성원을 중재자로 추가하고, 기본 설정을 설정할 수 있습니다.

채널 중재는 채널당 설정입니다. 채널 중재에 대한 테넌트 수준 설정은 없습니다. 테넌트 수준 채널 중재 설정을 추가하고자 하는 경우 [Teams UserVoice에서 요청하세요.](https://microsoftteams.uservoice.com/)

![manage-channel-moderation-in-teams-preferences.png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>채널에 대한 중재 켜기 또는 끄기

기본적으로 중재는 해제되어 있습니다. 즉, 일반적인 채널 설정이 팀 소유자 및 팀 구성원에게 적용됩니다. 예를 들어 새 게시물을 팀 구성원으로만 제한하거나 게스트를 포함한 모든 사용자가 새 게시물을 시작하도록 허용할 수 있습니다.

채널에 대한 중재를 켜려면 채널 중재에서 을 **클릭합니다.** 채널 중재가 설정될 때 중재자만 새 게시물을 시작할 수 있습니다. 

### <a name="add-or-remove-channel-moderators"></a>채널 중재자 추가 또는 제거

중재자 **아래에서** 관리를 클릭한 다음 팀 구성원을 중재자로 추가하거나 제거합니다. 팀 소유자와 중재자는 다른 중재자 추가 및 제거할 수 있습니다.  

### <a name="set-team-member-permissions"></a>팀 구성원 권한 설정

팀 **구성원 권한 아래에서** 허용할 활동 옆에 있는 확인란을 선택합니다.

## <a name="related-topics"></a>관련 항목

- [Teams의 팀 및 채널 개요](teams-channels-overview.md)
