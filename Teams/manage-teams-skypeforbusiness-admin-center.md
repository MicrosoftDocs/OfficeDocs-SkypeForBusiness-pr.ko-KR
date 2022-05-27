---
title: 새 Teams 관리 센터로 Teams 전환 관리
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 관리 센터 Teams 새 Teams 관리 센터로 전환하는 동안 Teams 대한 테넌트 전체 및 사용자 설정을 관리하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 83b65724099aa46bfe1f1719430e70d8da86ce33
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675090"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>새 Microsoft Teams 관리 센터로 전환하는 동안 팀 관리

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>새로운 Microsoft Teams 관리 센터란?  

새로운 관리 센터 환경을 통해 Teams 및 비즈니스용 Skype 모두 관리할 수 있는 통합된 환경을 제공합니다. 추가 기능, 엔드투엔드 인사이트 및 사용자 수준에서 Teams 설정을 관리하는 기능을 제공하고 있습니다.

![Microsoft Teams 관리 센터의 스크린샷.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>새 Microsoft Teams 관리 센터로 마이그레이션된 설정

다음 표에서는 마이그레이션된 Teams 환경의 섹션을 식별하고 현재 설정과 새 관리 포털의 정책 간의 관계를 보여 줍니다.

|Microsoft 365 관리 센터 Teams 섹션  |설정 이름(테넌트 수준)  |Microsoft Teams 관리 센터 정책   |수준: 테넌트 또는 사용자   |
|---------|---------|---------|---------|
|일반     |개인 프로필에 조직도 표시        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  테 넌 트       |
|일반     |Teams 없는 받는 사람에게 비즈니스용 Skype 사용         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |테 넌 트         |
|전자 메일 통합     |사용자가 채널에 전자 메일을 보낼 수 있도록 허용         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |테 넌 트         |
|전자 메일 통합     |보낸 사람 목록 허용         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |테 넌 트         |
|사용자 지정 클라우드 스토리지     |상자         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |테 넌 트         |
|사용자 지정 클라우드 스토리지     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |테 넌 트         |
|사용자 지정 클라우드 스토리지     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |테 넌 트         |
|사용자 지정 클라우드 스토리지     |Google 드라이브        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |테 넌 트         |
|사용자 지정 클라우드 스토리지     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |테 넌 트         |
|사용자/라이선스 유형별 설정     |모든 사용자에 대해 Microsoft Teams 켜거나 끕니다.          |사용되지 않는<sup>1</sup>        |         |
|팀 및 채널     |         |Azure Active Directory 그룹 관리로 리디렉션됩니다(현재 환경과 동일).              |사용자         |
|팀 및 채널     |         |AAD 그룹 관리(현재 환경과 동일)로 리디렉션됩니다.             |사용자          |
|앱|기본적으로 새 외부 앱 사용|조직 전체 앱 설정|테 넌 트|
|앱|외부 앱 허용|조직 전체 앱 설정|테 넌 트|
|앱|외부 앱의 테스트용 로드 허용<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|사용자|
|앱|기본 앱<sup>3</sup>|TeamsAppPermissionPolicy|사용자|
|앱|외부 앱<sup>3</sup>|TeamsAppPermissionPolicy|사용자|
|통화 및 모임     |비공개 모임 예약 허용         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |사용자          |
|통화 및 모임     |임시 채널 모임 허용         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |사용자          |
|통화 및 모임     |채널 모임 예약 허용         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |사용자          |
|통화 및 모임     |모임에서 비디오 허용         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |사용자          |
|통화 및 모임     |모임에서 화면 공유 허용         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |사용자          |
|통화 및 모임     |프라이빗 통화 허용         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |사용자          |
|메시징     |사용자가 대화에 GIF를 추가할 수 있도록 Giphy 사용         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |사용자         |
|메시징     |콘텐츠 등급         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |사용자         |
|메시징     |사용자가 편집하고 대화에 추가할 수 있는 밈 사용         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |사용자         |
|메시징     |사용자가 편집하고 대화에 추가할 수 있는 스티커 사용         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |사용자         |
|메시징     |소유자가 모든 메시지를 삭제하도록 허용         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |사용자         |
|메시징     |사용자가 자신의 메시지를 편집할 수 있도록 허용         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |사용자         |
|메시징     |사용자가 자신의 메시지를 삭제할 수 있도록 허용         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |사용자         |
|메시징     |사용자가 비공개로 채팅할 수 있도록 허용         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |사용자         |

<sup>1</sup> 게스트의 경우 더 이상 사용되지 않습니다. 이제 Microsoft Teams 관리 센터에서 게스트를 사용/사용하지 않도록 설정할 수 있습니다. 비즈니스 Enterprise, Edu Student 및 Edu 교직원용 Teams 사용/사용하지 않도록 설정하면 곧 더 이상 사용되지 않습니다. Microsoft 365 관리 센터 라이선스를 할당하여 관리해야 합니다. [Microsoft Teams 대한 사용자 액세스 관리를](user-access.md) 참조하세요.
<br><br>
<sup>2</sup> 사이드로딩은 다음과 같이 분할됩니다.

- 사용자가 [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)의 사용자 수준에서 관리할 수 있는 앱을 테스트용으로 로드하도록 허용합니다.
- 테넌트 사용자가 조직 전체 앱 설정에서 테넌트 수준에서 관리할 수 있는 사용자 지정 앱과 상호 작용할 수 있도록 허용합니다.

<sup>3</sup> TeamsAppPermissionPolicy의 사용자 수준에서 기본 앱 및 외부 앱을 사용하도록 설정하고 사용하지 않도록 설정할 수 있습니다. 또한 모든 사용자 및 테넌트 수준 설정을 재정의하는 조직 전체 앱 설정의 테넌트 수준에서 앱을 차단할 수 있습니다.

> [!NOTE]
> Teams 및 채널과 관련된 구성에는 Microsoft 365 관리 센터 그룹 대시보드를 계속 사용합니다. 앱용 설정 Microsoft 365 관리 센터 Teams 영역에 유지되며 나중에 마이그레이션됩니다.

## <a name="manage-settings-during-the-migration"></a>마이그레이션하는 동안 설정 관리

테넌트에 대한 섹션 마이그레이션이 완료될 때까지 Microsoft 365 관리 센터 및 비즈니스용 Skype 관리 센터에서 설정을 계속 수정할 수 있습니다.

다음 표에서는 마이그레이션 중에 기능을 관리할 수 있는 위치를 보여줍니다.

|기능  |Microsoft Teams 관리 센터                      |비즈니스용 Skype 관리 센터(레거시)  |Microsoft 365 관리 센터  |
|---------|:---------:|:---------:|:---------:|
|Teams 메시징, 모임 및 라이브 이벤트 정책     |     X    |         |         |
|Teams 업그레이드 정책     |    X     |         |         |
|메시징, 모임 및 음성에 대한 게스트 설정     |   X      |         |         |
|Teams 수명 주기 관리   |    X    |      |       |
|Teams 설정   |    X    |      |       |
|외부 액세스 설정     |    X    |      |       |
|사용자 관리    |         |         |    X     |
|오디오 회의     |    X     |    X     |         |
|통화 플랜     |    X    |    X     |         |
|전화 시스템    |    X    |     X    |         |
|전화 번호 관리     |    X    |   X      |         |
|클라우드 음성 기능 라이선싱     |         |         |    X     |
|자동 전화 교환     |    X    |          |         |
|통화 큐     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>마이그레이션 후 설정 관리

이러한 설정의 마이그레이션이 완료되면 Microsoft 365 관리 센터 및 비즈니스용 Skype 관리 센터에서 사용하지 않도록 설정하고 새 Microsoft Teams 관리 센터에서 관리할 수 있습니다.
