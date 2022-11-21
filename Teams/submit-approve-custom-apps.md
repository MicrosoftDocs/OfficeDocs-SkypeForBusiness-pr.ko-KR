---
title: Teams 앱 제출 API를 사용하여 사용자 지정 앱 제출 및 승인
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/19/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams의 Teams 앱 제출 API를 사용하여 제출한 사용자 지정 앱을 승인하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 83a4896fbd849cf55020854fd617da003d589cb0
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131267"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Teams 앱 제출 API를 통해 제출된 사용자 지정 앱 게시

이 문서에서는 Teams 앱을 개발에서 배포, 검색으로 전환하는 방법에 대한 종단 간 지침을 제공합니다. Teams가 앱 수명 주기 전체에 걸쳐 제공하는 연결된 환경을 간략하게 살펴보고 조직의 앱 스토어에서 사용자 지정 앱을 개발, 배포 및 관리하는 방법을 간소화할 수 있습니다.

개발자가 Teams 앱 제출 API를 사용하여 Microsoft Teams 관리 센터에 직접 사용자 지정 앱을 제출하여 검토하고 승인하는 방법, 조직 내 사용자를 위한 앱 관리 정책을 설정하는 방법, 사용자가 Teams에서 앱을 검색하는 방법 등 수명 주기의 각 단계를 다룹니다.

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="개발에서 배포까지의 앱 개요.":::

이 지침은 앱의 Teams 측면에 중점을 두고 있으며 관리자와 IT 전문가를 대상으로 합니다. Teams 앱 개발에 대한 자세한 내용은 [Teams 개발자 설명서](/microsoftteams/platform)를 참조하세요.

> [!NOTE]
> 사용자 지정 Teams 앱을 게시하면 조직의 앱 스토어에 있는 사용자가 사용할 수 있습니다. 사용자 지정 앱을 게시하는 방법에는 두 가지가 있으며 사용 방법은 앱을 얻는 방법에 따라 다릅니다. 이 문서에서는 개발자가 Teams 앱 제출 API를 통해 제출한 사용자 지정 앱을 승인하고 게시하는 방법에 대해 중점적으로 설명합니다. 사용자 지정 앱을 업로드하는 다른 방법은 개발자가 앱 패키지를 .zip 형식으로 보낼 때 사용됩니다. 해당 방법에 대한 자세한 내용은 [앱 패키지를 업로드하여 사용자 지정 앱 게시](/microsoftteams/upload-custom-apps)를 참조하세요. 승인 앱 위젯은 GCC 테넌트에서 사용할 수 없습니다.

> [!IMPORTANT]
> GCC 환경에서는 이 방법을 사용할 수 없습니다. [사용자 지정 앱을 업로드](upload-custom-apps.md)하여 GCC 환경에 게시합니다.

## <a name="develop"></a>개발

### <a name="create-the-app"></a>앱 만들기

Microsoft Teams 개발자 플랫폼을 사용하면 개발자가 자신의 앱과 서비스를 쉽게 통합하여 생산성을 높이고 더 빠르게 의사 결정을 내리며 기존 콘텐츠 및 워크플로를 중심으로 공동 작업을 수행할 수 있습니다. Teams 플랫폼에 구축된 앱은 Teams 클라이언트와 서비스 및 워크플로를 연결하여 공동 작업 플랫폼의 컨텍스트로 직접 가져옵니다. 자세한 내용은 [Teams 개발자 문서](/microsoftteams/platform)를 참조하세요.

### <a name="submit-the-app"></a>앱 제출

앱을 프로덕션에서 사용할 준비가 되면 개발자는 [Graph API](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), Visual Studio Code와 같은 IDE(통합 개발 환경) 또는 Power Apps, Power Virtual Agents와 같은 플랫폼에서 호출할 수 있는 Teams 앱 제출 API를 사용하여 앱을 제출할 수 있습니다. 이렇게 하면 Teams 관리 센터의 [앱 관리](/microsoftteams/manage-apps) 페이지에서 앱을 사용할 수 있으며, 여기서 앱을 검토하고 승인할 수 있습니다.

[Microsoft Graph 기반](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)인 Teams 앱 제출 API를 통해 조직은 원하는 플랫폼에서 개발하고 Teams의 사용자 지정 앱에 대한 제출-승인 프로세스를 자동화할 수 있습니다.

다음은 Visual Studio Code의 이 앱 제출 단계 예입니다.

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="Visual Studio 코드의 앱 제출 스크린샷":::

이 경우 아직 조직의 앱 스토어에 앱을 게시하지 않습니다. 이 단계에서는 조직의 앱 스토어에 게시하기 위해 앱을 승인할 수 있는 Teams 관리 센터에 앱을 제출합니다.

Graph API를 사용하여 앱을 제출하는 방법에 대한 자세한 내용은 [여기](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)를 참조하세요.

## <a name="notify"></a>알림

개발자가 검토 및 승인을 위해 새로운 응용프로그램을 제출할 때 알 수 있도록 알림을 설정할 수 있습니다. 개발자가 앱 업데이트를 제출할 때도 알림이 표시됩니다. Teams 관리 센터에서 앱 제출 알림을 사용하도록 설정하려면 **알림 및 경고** > **[경고](https://admin.teams.microsoft.com/notifications/rules)** > **앱 제출** 로 이동하고 상태를 **활성** 으로 변경하여 규칙을 활성화합니다. 기본적으로 이 설정은 꺼져 있습니다. 이 설정을 설정하려면 전역 관리자 또는 Teams 관리자여야 합니다.

이 설정을 켜면 **관리자 경고 및 알림** 팀의 **앱 제출** 이라는 새 채널 아래에 알림이 표시됩니다. 또는 기존 팀 및 채널을 선택하여 지정된 팀 및 채널로 알림을 받을 수 있습니다. 다음의 단계를 따릅니다:

1. **앱 제출** 규칙에서 **작업** 의 **채널 경고** 확인란을 선택합니다.
1. **채널 선택** 단추를 선택합니다.
1. 추가할 팀을 검색합니다.
1. 추가할 채널을 검색합니다.
1. **적용** 을 선택합니다.

   :::image type="content" source="media/channel-alert.png" alt-text="사용자 지정 채널 경고 알림 확인란" lightbox="media/channel-alert.png":::

> [!NOTE]
> **앱 제출** 채널의 **관리자 경고 및 알림** 팀에 알림을 받으려면 **기본 채널 경고** 확인란을 선택합니다.

:::image type="content" source="media/default-channel-alert.png" alt-text="기본 채널 경고 알림 확인란" lightbox="media/default-channel-alert.png":::

**웹후크** 확인란을 선택한 후 공용 웹후크 URL을 지정하여 외부 웹후크에 대한 알림을 설정할 수도 있습니다. JSON 알림 페이로드는 웹후크 URL로 전송됩니다.

:::image type="content" source="media/app-submission-notification.png" alt-text="앱 제출 알림" lightbox="media/app-submission-notification.png":::

앱 제출 규칙을 설정한 후에는 지정된 채널의 알림 카드를 검토하여 앱 세부 정보를 확인하고 **세부 정보 보기** 를 선택하여 Teams 관리 센터에서 앱을 열 수 있습니다.

## <a name="validate"></a>확인

Teams 관리 센터의 [앱 관리](/microsoftteams/manage-apps) 페이지(왼쪽 탐색에서 [**Teams 앱** > **앱 관리**](https://admin.teams.microsoft.com/manage-apps)로 이동)에서 조직의 모든 Teams 앱을 볼 수 있습니다. 페이지 맨 위에 있는 **승인 보류 중** 위젯을 통해 사용자 지정 앱이 승인을 위해 제출되는 시기를 알 수 있습니다.

테이블에 새로 제출된 앱은 자동으로 **게시 상태** 의 **제출됨** 과 **차단됨** **상태** 을 표시합니다. **게시 상태** 열을 내림차순으로 정렬하여 앱을 빠르게 찾을 수 있습니다.

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="게시 상태" lightbox="media/custom-app-lifecycle-validate-app.png":::

앱 이름을 클릭하면 앱 세부 정보 페이지로 이동합니다. **정보** 탭에서 설명, 상태, 제출자, 앱 ID 등 앱에 대한 세부 정보를 볼 수 있습니다.

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="제출된 앱의 앱 세부 정보 페이지" lightbox="media/custom-app-lifecycle-app-details.png":::

Graph API를 사용하여 **게시 상태** 를 확인하는 방법에 대한 자세한 내용은 [여기](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true)를 참조하세요.

## <a name="publish"></a>게시

사용자에게 앱을 제공할 준비가 되면 앱을 게시합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 로 이동합니다.
1. 앱 이름을 선택하여 앱 세부 정보 페이지로 이동한 다음 **게시 상태** 상자에서 **게시** 를 선택합니다.

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="앱 세부 정보 페이지의 게시 단추":::

앱을 게시하면 **게시 상태** 가 **게시됨** 으로 변경되고 **상태** 가 **허용됨** 으로 변경됩니다.

## <a name="set-up-and-manage"></a>설정 및 관리

### <a name="control-access-to-the-app"></a>앱에 대한 액세스 제어

기본적으로 조직의 모든 사용자는 조직의 앱 스토어에서 앱에 액세스할 수 있습니다. 앱 사용 권한이 있는 사용자를 제한하고 제어하기 위해 앱 권한 정책을 만들고 할당할 수 있습니다. 자세한 내용은 [Teams에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조하세요.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>사용자가 검색할 수 있도록 앱을 고정하고 설치하세요.

기본적으로 사용자가 앱을 찾으려면 조직의 앱 스토어로 이동하여 찾아보거나 검색해야 합니다. 사용자가 앱에 쉽게 액세스할 수 있도록 Teams의 앱 표시줄에 앱을 고정할 수 있습니다. 이렇게 하려면 앱 설정 정책을 만들고 사용자에게 할당합니다. 자세한 내용은 [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)를 참조하세요.

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams 앱 이벤트에 대한 감사 로그 검색

감사 로그를 검색하여 조직의 Teams 앱 활동을 볼 수 있습니다. 감사 로그를 검색하는 방법과 감사 로그에 기록된 Teams 활동 목록을 확인하는 방법에 대한 자세한 내용은 [Teams에서 이벤트에 대한 감사 로그 검색](audit-log-events.md)을 참조하세요.

감사 로그를 검색하려면 먼저 [보안 및 준수 센터](https://sip.protection.office.com/)에서 감사를 켜야 합니다. 자세한 내용은 [감사 로그 검색 설정 및 해제](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true)를 참조하세요. 감사 데이터는 감사가 켜진 시점부터만 사용할 수 있습니다.

## <a name="discover-and-adopt"></a>발견 및 채택

앱에 대한 권한이 있는 사용자는 조직의 앱 스토어에서 앱을 찾을 수 있습니다. 조직의 사용자 지정 앱을 찾으려면 앱 페이지에서 ***조직 이름*** 용으로 빌드로 이동하세요.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="게시된 앱을 보여주는 앱 페이지" lightbox="media/custom-app-lifecycle-discovery.png":::

앱 설정 정책을 만들고 할당한 경우 정책이 할당된 사용자가 쉽게 액세스할 수 있도록 앱이 Teams의 앱 표시줄에 고정됩니다.

## <a name="update"></a>업데이트

앱을 업데이트하려면 [개발](#develop) 섹션의 단계를 계속 따라야 합니다.

개발자가 게시된 사용자 지정 앱에 업데이트를 제출하면 [앱 관리](/microsoftteams/manage-apps) 페이지의 **승인 보류 중** 위젯에 알림 메시지가 표시됩니다. 표에서 앱의 **게시 상태** 는 **업데이트 제출됨** 으로 설정됩니다. 앱 제출 알림을 설정한 경우 **앱 제출** 채널의 **관리자 경고 및 알림** 팀에서도 알림 메시지가 표시됩니다. 알림 카드에는 Teams 관리 센터에 있는 앱으로 바로 이동할 수 있는 링크가 있습니다. 앱 제출 알림을 켜는 방법에 대한 자세한 내용은 [알림](#notify)을 참조하세요.

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="보류 중인 요청 및 앱 상태를 보여주는 앱 관리 페이지" lightbox="media/custom-app-lifecycle-update-submitted.png":::

앱 업데이트를 검토하고 게시하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 메뉴에서 **Teams 앱** > **앱 관리** 로 이동합니다.
1. 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 **사용 가능한 업데이트** 를 선택하여 업데이트 세부 정보를 검토합니다.

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="앱 세부 정보 페이지" lightbox="media/custom-app-lifecycle-update-app.png":::

1. 준비가 되면 **게시** 를 선택하여 업데이트를 게시합니다. 이렇게 하면 기존 앱이 교체되고, 버전 번호가 업데이트되며, **게시 상태** 항목이 **게시됨** 으로 변경됩니다. 모든 앱 권한 정책 및 앱 설정 정책은 업데이트된 앱에 계속 적용됩니다.

    업데이트를 거부하면 이전 버전의 앱이 게시된 상태로 유지됩니다.

이 경우 다음 사항을 유념해야 합니다.

* 앱이 승인되면 누구나 앱에 업데이트를 제출할 수 있습니다. 즉, 원래 앱을 제출한 개발자를 포함한 다른 개발자들이 앱에 업데이트를 제출할 수 있다는 것을 의미합니다.
* 개발자가 앱을 제출하고 요청이 보류 중인 경우 동일한 개발자만 앱에 업데이트를 제출할 수 있습니다. 다른 개발자는 앱이 승인되어야만 업데이트를 제출할 수 있습니다.

Graph API를 사용하여 앱을 업데이트하는 방법에 대한 자세한 내용은 [여기](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true)를 참조하세요.

## <a name="related-articles"></a>관련 기사

* [앱 패키지를 업로드하여 사용자 지정 앱 게시](upload-custom-apps.md)
* [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
* [사용자 지정 앱에 대한 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
* [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
* [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
* [Teams 모니터링 및 경고](alerts/teams-admin-alerts.md)
* [Teams용 Microsoft Graph API 앱](alerts/teams-admin-alerts.md)
