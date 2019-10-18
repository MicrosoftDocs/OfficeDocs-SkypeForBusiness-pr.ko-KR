---
title: Microsoft 팀에서 채널 중재 설정 및 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
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
description: 팀 구성원을 채널 중재자로 추가 하는 방법을 포함 하 여 Microsoft 팀에서 중재를 위해 채널을 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 52b89f21cd2b622b78f6dbee44d8efe5ce4ce490
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570666"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Microsoft 팀에서 채널 중재 설정 및 관리

Microsoft 팀에서 팀 소유자는 채널에 대 한 중재를 설정 하 여 새 게시물을 시작 하 고 해당 채널의 게시물에 회신할 수 있는 사용자를 제어할 수 있습니다.

팀 소유자는 팀 구성원을 중재자로 추가할 수도 있습니다. 팀 소유자는 채널 수준에 대 한 실무 전문성을 제공 하지 않을 수 있으며 채널 중재를 최적화 하는 데 도움이 됩니다. 특정 팀 멤버가 채널을 중간에 할 수 있도록 허용 하 여 채널 내에서 콘텐츠 및 컨텍스트를 관리 하는 책임은 팀 소유자와 채널 중재자 간에 공유 됩니다. 예를 들어 팀 소유자는 비즈니스 소유자 또는 콘텐츠 소유자를 중재자로 추가 하 여 해당 채널에서 정보 공유를 제어할 수 있습니다.

## <a name="what-can-a-channel-moderator-do"></a>채널 중재자는 어떤 작업을 할 수 있나요?

채널 중재자는 다음을 수행할 수 있습니다.

- 채널에서 새 게시물을 시작 합니다. 채널에 대 한 중재가 설정 되어 있는 경우 중재자만 해당 채널에서 새 게시물을 시작할 수 있습니다.
- 팀 구성원을 한 채널에 대 한 중재자로 추가 하 고 제거 합니다. 기본적으로 팀 소유자는 채널 중재자 이며 제거할 수 없다는 점에 유의 하세요.
- 팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부와 인공 지능 및 커넥터에서 채널 메시지를 제출할 수 있는 여부를 제어 합니다.

## <a name="scenarios"></a>등

다음은 조직에서 팀의 채널 중재를 사용 하는 방법에 대 한 몇 가지 예입니다.

### <a name="use-a-channel-as-an-announcement-channel"></a>채널을 알림 채널로 사용

마케팅 팀은 특정 채널을 사용 하 여 주요 프로젝트 공지 사항 및 결과물을 공유 합니다. 팀 구성원이 다른 채널에 더 적절 한 콘텐츠를 채널에 게시 하는 경우가 있습니다. 팀 소유자는 팀 구성원이 해당 채널을 사용 하 여 중요 한 역할을 할 수 있도록 채널의 정보 공유를 알림만 제한 하려고 합니다.

이 시나리오에서 팀 소유자는 마케팅 잠재 고객을 중재자로 추가 하 여 채널에 알림을 게시 하 고 팀 구성원이 해당 채널의 메시지에 회신 하는 기능을 해제할 수 있습니다.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>교육 팀에서 수업 토론을 위해 채널 사용

교육 팀에서 과학 교사는 채널을 사용 하 여 특정 강의실 주제에 대 한 중요 한 토론에 참여 합니다.

이 시나리오에서 교사는 해당 조교의 교육 도우미를 사용 하 여 채널을 중간에 할 수 있습니다. 그런 다음 교육 도우미가 학생 들과 함께 토론을 시작 하 고 드라이브를 만드는 새 게시물을 만들 수 있습니다.

## <a name="manage-channel-moderation"></a>채널 중재 관리

팀에서 채널로 이동 하 고 **기타 옵션 ...** 을 클릭 합니다.  >  **채널을 관리**합니다. 여기서는 중재 기능을 설정 및 해제 하 고 팀 구성원을 중재자로 추가 하 고 기본 설정을 지정할 수 있습니다.

채널 중재는 채널 별로 설정 된 것입니다. 채널 중재에 대 한 테 넌 트 수준 설정은 없습니다. 테 넌 트 수준 채널 중재 설정을 추가 하려면 [팀 UserVoice](https://microsoftteams.uservoice.com/)에 요청 하세요.

![manage-channel-moderation-in-teams-preferences](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>채널에 대 한 중재 설정 또는 해제

기본적으로 중재는 해제 되어 있으며,이는 일반적인 채널 설정이 팀 소유자 및 팀 구성원에 게 적용 됨을 의미 합니다. 예를 들어 새 게시물을 팀 구성원 으로만 제한 하거나 게스트를 포함 하 여 모든 사용자가 새 게시물을 시작 하도록 할 수 있습니다.

채널에 대 한 중재를 설정 하려면 **채널 중재** **에서 설정을 클릭 합니다**. 채널 중재가 설정 되어 있는 경우 중재자만 새 게시물을 시작할 수 있습니다. 

### <a name="add-or-remove-channel-moderators"></a>채널 중재자 추가 또는 제거

**중재자**인 경우 **관리**를 클릭 한 다음 팀 구성원을 중재자로 추가 하거나 제거 합니다. 팀 소유자와 중재자는 다른 중재자를 추가 하 고 제거할 수 있습니다.  

### <a name="set-team-member-permissions"></a>팀 구성원 권한 설정

**팀 구성원 권한**에서 허용 하려는 작업 옆에 있는 확인란을 선택 합니다.

## <a name="related-topics"></a>관련 항목

- [팀의 팀 및 채널 개요](teams-channels-overview.md)
