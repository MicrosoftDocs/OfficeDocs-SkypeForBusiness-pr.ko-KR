---
title: Microsoft Teams의 조직 전체 팀을 사용하여 모든 사용자가 공동 작업할 수 있도록 지원
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Teams에서 조직 전체 팀을 만들고 관리하여 중소 규모의 조직의 모든 사용자가 공동 작업할 수 있는 방법을 제공하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- EngageScoreOct2022
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3ae5ffc68d14b9998721010e8f6b8ed595ac26e9
ms.sourcegitcommit: 6d2e4f5e09b22a8192405f4eba90960a152032d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2022
ms.locfileid: "68885081"
---
# <a name="use-organization-wide-teams-in-microsoft-teams-to-help-everyone-collaborate"></a>Microsoft Teams의 조직 전체 팀을 사용하여 모든 사용자가 공동 작업할 수 있도록 지원

글로벌 관리자는 중소 규모의 조직의 모든 사람이 단일 공동 작업 팀의 일원이 될 수 있는 방법을 제공하는 조직 전체 팀을 만들 수 있습니다. 조직 전체 팀은 자동으로 조직의 모든 사용자를 포함하고 사용자가 조직에 가입하고 나갈 때 멤버 자격을 최신 상태로 유지합니다.

조직이 Teams를 익숙하지 않고 사용자가 5,000명 이하인 경우 조직 전체 팀이 자동으로 만들어집니다. 조직 전체 팀은 사용자가 10,000명 이하인 조직으로 제한됩니다. 조직 전체 팀을 최대 5개까지 포함할 수 있습니다. 

## <a name="create-an-organization-wide-team"></a>조직 전체 팀 만들기

조직 전체 팀을 만드는 방법에는 두 가지가 있습니다.

- 기존 팀을 조직 전체 팀으로 변환합니다. 팀 이름으로 이동하고 **기타 옵션** > **팀 편집** 을 클릭합니다.

- [처음부터 새 팀을 만들고](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b) **조직 전체** 옵션을 선택합니다.

    ![조직 전체 팀을 만드는 조직 전체 옵션의 스크린샷.](media/create-org-wide-team.png "조직 전체 팀을 만들기 위한 조직 전체 옵션의 스크린샷")

## <a name="types-of-users-in-an-organization-wide-team"></a>조직 전체 팀의 사용자 유형

조직 전체 팀이 만들어지면 모든 전역 관리자 및 Teams 관리자가 팀 소유자로 추가되고 모든 활성 사용자가 팀 구성원으로 추가됩니다. 팀 구성원은 조직 전체 팀을 떠날 수 없지만 팀 소유자는 필요한 경우 사용자를 수동으로 추가하거나 제거할 수 있습니다. Teams에서 사용자를 자동으로 추가하거나 제거하면 일반 채널로 알림이 전송됩니다.

라이선스가 없는 사용자도 팀에 추가됩니다. 허가되지 않은 사용자가 Teams에 처음 로그인하면 Microsoft Teams Exploratory 라이선스가 할당됩니다. Exploratory 라이선스에 대한 자세한 내용은 [Microsoft Teams Exploratory 라이선스 관리를 참조하세요](teams-exploratory.md).

다음 유형의 계정은 조직 전체 팀에 추가되지 않습니다.

- 로그인이 차단된 계정
- 게스트
- 리소스 또는 서비스 계정(예: 자동 전화 교환 및 통화 큐와 연결된 계정)
- 회의실 또는 장비 계정
- 공유 사서함으로 지원되는 계정

> [!NOTE]
> 회의실 목록, 장비 및 리소스 계정의 일부가 아닌 회의실을 조직 전체 팀에 추가하거나 동기화할 수 있습니다. 팀 소유자는 팀에서 이러한 계정을 쉽게 제거할 수 있습니다.

## <a name="options-to-get-the-most-out-of-an-organization-wide-team"></a>조직 전체 팀을 최대한 활용하기 위한 옵션

조직 전체 팀을 최대한 활용하려면 팀 소유자가 다음 작업을 수행하는 것이 좋습니다.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>팀 소유자만 일반 채널에 게시하도록 허용

팀 소유자만 일반 채널에 게시하여 채널 "소음"을 줄일 수 있습니다.

1. 팀으로 이동하여 일반 채널을 찾은 다음... 를 선택합니다 **. 추가 옵션** > **채널 관리**.
2. **채널 설정** 탭에서 **사용 권한을** 클릭한 다음 **소유자만 메시지를 게시할 수 있습니다** 를 선택합니다.

### <a name="turn-off-team-and-team-name-mentions"></a>@팀 및 @[팀 이름] 멘션 해제

전체 조직에 과부하가 되는 것을 방지하기 위해 @멘션을 줄입니다.

1. 팀으로 이동하여 **... 추가 옵션** \> **팀 관리**.
2. **설정** 탭에서 **@mentions** \> 구성원 **에게 @team 옵션 표시 또는 @[팀 이름]을** 끕니다.

### <a name="automatically-show-important-channels"></a>중요한 채널 자동 표시

중요한 채널을 표시하여 조직의 모든 사용자가 특정 대화에 참여할 수 있도록 합니다. 자세한 내용은 [전체 팀에 대해 채널을 자동으로 즐겨찾기에 추가](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)를 참조하세요.

### <a name="set-up-channel-moderation"></a>채널 중재 설정

채널 중재를 설정하고 특정 팀 구성원에게 중재자 역할을 제공할 수 있습니다. (조정이 설정되면 팀 소유자에게 자동으로 중재자 기능이 제공됩니다.) 중재자는 다음을 수행할 수 있습니다.

- 채널에서 새 게시물을 시작할 수 있는 사람 제어
- 중재자 추가 및 제거
- 팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부 제어
- 봇 및 커넥터가 채널 메시지를 제출할 수 있는지 여부를 제어합니다.

자세한 정보는 [Microsoft Teams에서 채널 조정 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조하세요.

### <a name="remove-accounts-that-might-not-belong"></a>소속되지 않은 계정 삭제

구성원이 조직 전체 팀을 떠날 수는 없지만 팀 소유자로서 소속되지 않은 계정을 제거하여 팀 명단을 관리할 수 있습니다. **Teams를 사용하여 조직 전체 팀에서 사용자를 제거하도록 합니다**. Microsoft 365 관리 센터 또는 Outlook의 그룹에서 사용자를 제거하는 다른 방법을 사용하는 경우 사용자가 조직 전체 팀에 다시 추가될 수 있습니다.

## <a name="related-topics"></a>관련 주제

[Microsoft Teams에서 조직 전체 팀을 만드는 방법에](https://www.youtube.com/watch?v=x3qGlwwCz_w) 대한 비디오를 시청하세요.
