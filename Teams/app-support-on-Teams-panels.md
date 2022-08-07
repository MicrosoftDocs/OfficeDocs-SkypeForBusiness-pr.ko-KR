---
title: Teams 패널에서 Microsoft Teams 앱/LOB(기간 업무) 앱 지원
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Teams 앱/LOB 앱에 대한 지원을 설명합니다.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75548acc44d1f360e13dd5946e6e39726c744bb6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270683"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Teams 패널에서 Microsoft Teams 앱/LOB(기간 업무) 앱 지원

Teams 패널은 [Teams 앱/LOB(기간 업무) 앱](/microsoftteams/platform/overview)에 대한 지원을 추가하고 있습니다. 이를 통해 기업은 조직의 요구 사항에 맞게 패널에 추가 환경을 추가할 수 있습니다. 이 릴리스는 정적 웹 콘텐츠를 지원합니다.

> [!IMPORTANT]
> 이 기능은 Teams 패널 디바이스를 업데이트한 후에만 사용할 수 있습니다. Teams 패널 내에서 앱을 지원하려면 Teams 앱 버전 1449/1.0.97.2021070601 이상이 있어야 합니다.

## <a name="teams-app-experience-on-teams-panels"></a>Teams 패널의 Teams 앱 환경

![사용자가 앱으로 이동할 수 있는 섹션을 보여 주는 Teams 관리 센터의 스크린샷.](media/tac1update.png)

*Teams 패널 홈 화면에는 빨간색 스크린샷에 설명된 앱 탐색 옵션이 포함되어 있습니다. 이러한 아이콘은 예제 아이콘이며 사용할 수 없습니다.*

![앱을 추가할 수 있는 앱 캔버스의 스크린샷.](media/appscreen.png)

*최종 사용자가 앱 아이콘 중 하나를 탭하면 이전 스크린샷에 Teams 앱 화면이 표시됩니다. 스크린샷의 회색 사각형은 Teams 패널 앱이 표시되는 위치입니다. 앱 바는 고정되어 있으며 Teams 패널 앱의 일부입니다.*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Teams 관리 센터에서 Teams 패널 앱 설정 및 관리

Microsoft Teams 앱은 주요 정보, 일반 도구 및 신뢰할 수 있는 프로세스를 사람들이 수집하고, 배우고, 작업하는 곳으로 가져옵니다. Teams 앱 [은 통합된 기능을 통해 작동합니다](/microsoftteams/platform/concepts/capabilities-overview). 이제 IT 관리자가 조직의 Teams 패널 디바이스에 포함할 앱을 선택하고 [Teams 관리 센터를](https://admin.teams.microsoft.com/) 통해 사용 권한을 사용자 지정할 수 있습니다.

이제 Teams 패널에서 Teams 앱을 사용하고 조직의 요구에 따라 사용자 환경을 사용자 지정할 수 있습니다. 사용자가 앱 보기에 액세스하고 사용하고 우선 순위를 지정할 수 있는 웹앱을 결정할 수 있습니다. 봇 및 메시징 기능과 같은 일부 옵션은 현재 지원되지 않습니다. [Teams 앱](/microsoftteams/platform/overview) 및 [Microsoft Teams에서 디바이스를 관리하는 방법에](/microsoftteams/devices/device-management) 대해 자세히 알아봅니다.

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Teams 관리 센터의 Teams 패널에서 앱 관리

**참고**: [Teams 관리 센터에](https://admin.teams.microsoft.com/) 액세스하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.

최종 사용자는 Teams 패널에서 앱을 볼 수 있지만 설치할 수는 없습니다. 관리자는 Teams 관리 센터를 통해 조직의 모든 Teams 앱을 보고 관리할 수 있습니다. 앱 **관리** 페이지를 통해 [Microsoft Teams 관리 센터에서 앱을 관리하는](/microsoftteams/manage-apps) 방법에 대해 자세히 알아봅니다. Teams 관리 센터 내의 **앱 관리** 페이지에서 [도 사용자 지정 앱을](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store) 업로드할 수 있습니다.

앱을 설정한 후 [앱 사용 권한 정책](/microsoftteams/teams-app-permission-policies) 및 [앱 설정 정책을](/microsoftteams/teams-app-setup-policies) 사용하여 조직의 특정 회의실 계정에 대한 앱 환경을 구성할 수 있습니다.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>앱 설정 정책을 사용하여 Teams 패널에 앱 고정

Teams는 다양한 앱을 표시할 수 있는 기능을 제공하므로 관리자는 조직에 가장 필수적인 앱을 결정하고 빠른 액세스를 위해 Teams 패널 **홈** 화면에만 고정할 수 있습니다. 고정된 앱이 5개 이상 있거나 고정되지 않은 앱이 있는 경우 **추가** 화면 아래에 표시됩니다. Microsoft는 Teams 패널용으로 특별히 사용자 지정 앱 설정 정책을 만드는 것이 좋습니다.

![앱 설정 정책 페이지의 사용자 인터페이스 스크린샷.](media/appsetup1.png)

Teams 패널에 표시된 고정된 앱을 관리하려면 조직의 Teams 관리 센터에 로그인하고 **Teams 앱** \> **설정 정책** \> **선택 또는 새 정책** \> **고정 앱** 만들기로 이동합니다.

![사용자 인터페이스 내의 고정된 앱 섹션 스크린샷](media/appsetup2.png)

*이 이미지에 포함된 앱은 예제일 뿐이며 사용할 수 없습니다.*

Microsoft는 Teams 패널에서 최상의 Teams 앱 환경을 위해 **사용자 지정 앱 업로드** 및 **사용자 고정** 을 해제하는 것이 좋습니다.

앱 고정에 대한 자세한 내용은 [앱 설정 정책 관리를](/microsoftteams/teams-app-setup-policies) 참조하세요.

## <a name="manage-apps-display-order-in-teams-panels"></a>Teams 패널에서 앱 표시 순서 관리

![사용자 인터페이스 내의 앱 섹션 스크린샷](media/appsetup3.png)

*이 이미지에 포함된 앱은 예제일 뿐이며 사용할 수 없습니다.*

Teams 패널에 앱이 표시되는 순서를 관리하려면 조직의 Teams 관리 센터에 로그인하고 **Teams 앱** \> **설정 정책** \> 으로 이동하여 **정책** \> **고정 앱 선택:** **이동/축소** 를 선택합니다.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>회의실 리소스 계정에 설정 정책 할당

설치 정책을 만든 후 관리자는 Teams 패널에 로그인할 회의실 리소스 계정에 이 정책을 할당해야 합니다. 자세한 내용은 [사용자 및 그룹에 정책 할당을 참조하세요](/microsoftteams/assign-policies-users-and-groups).

## <a name="faq"></a>FAQ

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Teams 패널이 새 앱 또는 업데이트된 앱 설정 정책을 가져오는 데 얼마나 걸리나요?

Teams 관리 센터에서 새 정책을 편집하거나 할당한 후 변경 내용을 적용하는 데 최대 24시간이 걸릴 수 있습니다. 관리자는 패널에서 로그아웃/로그인을 시도하고 **설정 아이콘을** 탭한 다음 **홈** 화면으로 돌아가 정책을 새로 고치려고 할 수 있습니다.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>"자세히" 화면에서 앱의 순서는 무엇인가요?

**추가** 앱 페이지에서 고정된 앱이 먼저 표시됩니다. 그런 다음 설치된 다른 앱이 사전순으로 표시됩니다.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Teams 패널에 봇 앱이 표시되지 않는 이유는 무엇인가요?

현재 정적 탭 웹 콘텐츠만 지원됩니다.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>일정 및 작업과 같은 네이티브 Teams 앱이 Teams 패널에 표시되지 않는 이유는 무엇인가요?

일정 및 작업과 같은 네이티브 Teams 앱은 Teams 패널에 표시되지 않습니다.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Teams 관리 센터의 설치 정책 섹션에서 설치된 앱과 고정된 앱의 차이점은 무엇인가요?

Teams 패널의 경우 관리자가 원하는 앱을 선택하고 순서를 다시 정렬할 수 있도록 고정된 앱을 사용하는 것이 좋습니다.

**참고:** 일부 앱은 앱 고정을 지원하지 않습니다. 앱 고정 기능을 사용하도록 설정하려면 앱 개발자에게 문의하세요.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Teams 앱 설정 정책 섹션에 설치되거나 고정된 앱에 속하지 않더라도 다른 앱이 "자세히" 화면에 표시되는 이유는 무엇인가요?

앱이 이전에 다른 앱 정책을 통해 설치되었거나 Teams 패널에 사용된 회의실 리소스 계정의 Teams 데스크톱/웹 클라이언트에 수동으로 설치된 경우 관리자는 Teams의 회의실 리소스 계정에 로그인하고 앱을 마우스 오른쪽 단추로 클릭한 다음 **제거** 를 선택하여 앱을 수동으로 제거해야 할 수 있습니다.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>"고정된 앱 추가" 창에서 앱을 찾을 수 없는 이유는 무엇인가요?

앱 설정 정책을 통해 모든 앱을 Teams에 고정할 수 있는 것은 아닙니다. 일부 앱은 이 기능을 지원하지 않을 수 있습니다. 고정할 수 있는 앱을 찾으려면 **고정된 앱 추가** 창에서 앱을 검색합니다. 자세한 내용은 [앱 설정 정책 작업의 FAQ](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)를 참조하세요.

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>"사용자 고정"을 해제한 후 설정 정책 패널에 "사용자 고정" 팝업이 표시되는 이유는 무엇인가요?

![사용자 고정이 활성 상태임을 확인하는 팝업이 있는 사용자 인터페이스 내의 설정 정책 섹션 스크린샷.](media/appsetup4.png)

*이 이미지에 포함된 앱은 예제일 뿐이며 사용할 수 없습니다.*

이 동작은 공유 공간의 디바이스에 대해 예상되며 의도하지 않은 앱 고정을 방지하는 데 도움이 됩니다.
