---
title: 조직에 대한 설정 관리
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: 앱, 외부 액세스, 게스트 액세스, Teams 설정, Teams 업그레이드 기본 설정을 포함하여 Microsoft Teams 조직 전체 설정을 켜거나 끄는 방법을 알아봅니다.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.teamssettings.targetingintro
- ms.teamsadmincenter.teamssettings.overview
- NewAdminCenter_Update
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b9145854008753cf5c0d1f5915096766689c68b
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739246"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>조직에서 Microsoft Teams 설정 관리

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터의 Teams 앱 설정

[Microsoft Teams 관리 센터](https://admin.teams.microsoft.com)의 **Teams 앱**에서 조직의 앱을 관리합니다. 예를 들어, 조직 전체 또는 특정 Teams 사용자에게 사용할 수 있는 앱을 제어하는 정책을 설정하고, 사용자에게 가장 중요한 앱을 고정하여 Teams를 사용자 지정할 수 있습니다.

자세한 내용은 [Team에서 앱에 대한 관리 설정](admin-settings.md)을 참조하세요.  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터의 Teams 조직 전체 설정

Microsoft Teams 관리 센터에서 조직 전체 사용자 설정을 제어할 수 있습니다. 조직 전체 설정을 편집하려면 Microsoft Teams 관리 센터로 이동한 후 **조직 전체 설정**을 선택합니다. 다음과 같은 설정을 구성할 수 있습니다.

### <a name="external-access"></a>외부 액세스

**외부 액세스**를 사용하면 Teams와 비즈니스용 Skype 사용자가 조직 또는 도메인 외부의 사용자와 통신할 수 있습니다. 외부 액세스를 구성하려면 [Teams 사용자가 다른 Teams 조직의 사용자와 채팅하고 커뮤니케이션하도록 허용](let-your-teams-users-communicate-with-other-people.md)으로 이동합니다.

도메인을 추가하거나 차단하려면 다음을 수행합니다.

1. **도메인 추가**를 선택합니다.
2. 도메인 추가 창에서 도메인 이름을 입력하고 스페이스바를 클릭하여 이름을 저장합니다.
3. **허용됨** 또는 **차단됨**을 선택합니다.
4. **완료**를 선택하여 변경 내용을 저장합니다. 

### <a name="guest-access"></a>게스트 액세스

Microsoft Teams의 **게스트 액세스**를 사용하면 조직의 팀에서 팀과 채널에 대한 액세스 권한을 부여하여 조직 외부의 사용자와 공동 작업을 할 수 있습니다. 비즈니스 또는 소비자 전자 메일 계정(Outlook, Gmail 등)이 있는 사용자는 팀 채팅, 모임 및 파일에 대한 모든 액세스 권한을 부여받아 Teams에서 게스트로 참여할 수 있습니다. 자세한 내용은 [Microsoft Team의 게스트 액세스](guest-access.md)를 참조하세요.

### <a name="teams-settings"></a>Teams 설정

**Teams 설정**에서 알림과 피드, 전자 메일 통합, 클라우드 저장소 옵션 및 디바이스를 포함하는 Teams의 기능을 설정할 수 있습니다.

#### <a name="notifications-and-feeds"></a>알림 및 피드

Teams의 사용자 활동 피드에 제안된 피드를 표시할지 여부를 제어할 수 있습니다. 활동 피드에 대한 자세한 내용은 [Teams에서 활동 피드 둘러보기](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)를 참조하세요.

#### <a name="tagging"></a>태그 지정

태그를 사용하면 사용자가 팀의 사람들과 의사 소통할 수 있습니다. 하나 이상의 팀 구성원에게 태그를 추가할 수 있습니다. 태그를 추가한 후 채널 게시물의 모든 팀 구성원은 @mentions에서 태그를 사용하여 해당 태그가 지정된 사람과만 의사 소통할 수 있습니다. 이 설정을 사용하여 태그를 추가할 수 있는 사용자와 조직 전체에서 태그를 사용하는 방법을 제어하세요. 자세한 내용은 [Teams에서 태그 관리](manage-tags.md)를 참조하세요.

#### <a name="email-integration"></a>전자 메일 통합

사용자가 채널 전자 메일 주소를 사용하여 Teams의 채널에 전자 메일을 보낼 수 있도록 하려면 이 기능을 켭니다. 사용자는 자신이 소유한 팀에 속한 모든 채널에 대해 이 작업을 수행할 수 있습니다. 사용자는 Teams 구성원을 위해 커넥터 추가를 설정한 팀의 모든 채널로 전자 메일을 보낼 수도 있습니다. 전자 메일 통합을 설정하려면 **사용자가 채널 전자 메일 주소에 전자 메일을 보낼 수 있도록 허용**이 **켬**인지 확인합니다.

#### <a name="files"></a>파일

여기서 파일 공유 및 클라우드 파일 저장소 옵션을 켜거나 끌 수 있습니다.

사용자는 Teams 채널과 채팅의 클라우드 저장소 서비스에서 파일을 업로드하고 공유할 수 있습니다. Teams의 클라우드 저장소 옵션에는 현재 Dropbox, Box, ShareFile, Google Drive및 Egnyte(곧 지원됨)가 포함됩니다. 조직에서 사용하려는 클라우드 저장소 공급자에 대한 스위치를 켭니다.

#### <a name="organization"></a>조직

여기에서 사용자 조직에 대한 세부 조직 차트를 보여 주는 **조직** 탭을 켤 수 있습니다. 자세한 내용은 [Teams에서 조직 탭 사용](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)을 참조하세요.

#### <a name="devices"></a>디바이스

이 설정은 Microsoft Teams 모임에 참석하는 Surface Hub 디바이스에 대한 리소스 계정 동작을 제어합니다. 이 설정을 사용하여 인증 요구 사항을 구성하고, 콘텐츠 PIN을 요구하고, 메시지를 보낼 Surface Hub 리소스 계정을 켭니다.

- **모임 콘텐츠에 액세스하기 위해 보조 인증 형식을 요구합니다.** - 콘텐츠 PIN을 입력할 때의 사용자의 액세스 수준을 선택합니다.
- **콘텐츠 PIN 설정** – 사용자는 문서에 대한 무단 액세스를 방지하기 위해 이 PIN을 입력해야 합니다. 이렇게 하면 권한이 없는 사용자는 예정된 모임에 참석하거나 첨부 파일을 검색할 수 없습니다.
- **리소스 계정은 메시지를 보낼 수 있습니다.** - Surface Hub 리소스 계정에서 메시지를 보낼 수 있도록 하려면 이 설정을 **켬**으로 지정합니다.

#### <a name="search-by-name"></a>이름으로 검색

Microsoft Teams 범위 디렉터리 검색은 Exchange APB(주소록 정책)를 사용하여 조직에서 사용자가 조직의 다른 사용자를 찾고 커뮤니케이션하는 방법을 제어하는 가상 경계를 만들 수 있도록 합니다. 다음과 같은 경우 범위 디렉터리 검색을 사용하는 것이 좋습니다.

- 조직의 테넌트 내에 별도로 유지하려는 여러 회사가 있는 경우 
- 학교에서 교사와 학생 간의 채팅을 제한하려고 하는 경우 

범위 디렉터리 검색을 설정하려면 이 설정을 **켬**으로 전환합니다.

### <a name="skype-for-business"></a>비즈니스용 Skype

이 페이지를 사용하여 조직에서 비즈니스용 Skype 사용자를 위해 비즈니스용 Skype 기능을 관리할 수 있습니다. 자세한 내용은 [Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리](skype-for-business-settings.md)를 참조하세요.

### <a name="teams-upgrade"></a>Teams 업그레이드

이러한 설정을 사용하여 비즈니스용 Skype에서 Microsoft Teams로 사용자를 업그레이드하는 방법을 구성할 수 있습니다. 

#### <a name="coexistence-mode"></a>공존 모드
다음과 같은 공존 모드를 지정할 수 있습니다. 

- **Teams 전용**
- **Islands**(Teams와 비즈니스용 Skype의 공존)
- **비즈니스용 Skype 전용**
- **Teams 공동 작업이 포함된 비즈니스용 Skype**(사용자는 비즈니스용 Skype로 채팅 및 통화를 받고 모임을 예약하지만 그룹 공동 작업을 위해 Teams를 사용함)
- **Teams 공동 작업 및 모임이 포함된 비즈니스용 Skype**(사용자는 비즈니스용 Skype로 채팅 및 통화를 받지만, 그룹 공동 작업 및 모임 예약을 위해 Teams를 사용함)

선택하는 공존 모드는 수신 통화 및 채팅의 라우팅과 사용자가 채팅 및 통화를 시작하거나 모임을 예약하는 데 사용하는 앱을 결정합니다. 공존 모드에 대한 자세한 내용은 [Microsoft Teams와 비즈니스용 Skype의 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md)로 이동하세요.

#### <a name="app-preferences"></a>앱 기본 설정

여기에서 사용자가 비즈니스용 Skype 모임(비즈니스용 Skype 또는 [Skype 모임 앱](https://support.office.com/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5))에 참가하기 위해 사용하는 앱을 선택할 수 있습니다. 이 설정은 공존 모드 설정에 따라 달라집니다.


#### <a name="network-planner"></a>Network Planner

Network Planner를 통해 조직 전체에 팀 사용자를 연결하는데 필구한 네트워크 요건을 판단하고 구성하는데 도움을 받을 수 있습니다.  [Microsoft Teams용 Network Planner 사용](https://docs.microsoft.com/microsoftteams/network-planner) 방법을 알아보세요.

"비즈니스용 Skype 사용자를 위해 백그라운드에서 Teams 앱 다운로드" 옵션도 선택할 수 있습니다.  기본적으로, 이 설정은 켬으로 설정되어 있습니다. 이 설정을 사용하도록 설정하면 Windows PC에서 비즈니스용 Skype 앱을 실행하는 사용자를 위해 Teams 앱이 백그라운드로 다운로드됩니다. 사용자에 대한 동시 사용 모드가 Teams 전용이거나 보류 중인 업그레이드 알림이 비즈니스용 Skype 앱에서 활성화된 경우 이와 같이 작동합니다.


## <a name="how-can-i-tell-which-features-are-available"></a>어떤 기능을 사용할 수 있는지 어떻게 알 수 있나요?

새 Teams 기능에 대한 내용은 [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)을 참조하세요. 새 기능 및 예정된 기능에 대한 자세한 내용은 Teams의 [새로운 기능](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) 페이지 및 Teams의 [기술 커뮤니티 Microsoft Teams 블로그](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)를 참조하세요. 

## <a name="more-information"></a>추가 정보

관리자 기능을 수행할 수 있는 역할에 대한 내용은 [Microsoft Teams 관리자 역할을 사용하여 Teams 관리](using-admin-roles.md)를 참조하세요.
