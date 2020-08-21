---
title: Teams 앱 제출 API를 사용하여 사용자 지정 앱 제출 및 승인
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams에서 Teams 앱 제출 API를 사용하여 제출된 사용자 지정 앱을 승인하는 방법을 알아봅니다.
ms.openlocfilehash: bdd13dbe4db46110250ea380eebd0ea1d011a322
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824919"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Teams 앱 제출 API를 통해 제출된 사용자 지정 앱 게시

## <a name="overview"></a>개요

> [!NOTE]
> 사용자 지정 Teams 앱을 퍼블리싱하면 조직의 앱 스토어에 있는 사용자가 이 앱을 사용할 수 있습니다. 사용자 지정 앱을 게시하는 두 가지 방법과 앱을 사용하는 방법은 그 방법에 따라 다를 수 있습니다. **이 문서는 개발자가 Teams 앱 제출 API를**통해 제출하는 사용자 지정 앱을 승인하고 게시하는 방법에 대해 집중적으로 설명합니다. 또 다른 방법은 개발자가 앱 패키지를 .zip 형식으로 보낼 때 사용됩니다. 이 방법에 대한 자세한 내용은 앱 <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">패키지를 업로드하여 사용자 지정 앱 게시를 참고하세요.</a>
 
이 문서는 Teams 앱을 개발부터 배포까지 배포까지 이동하는 방법에 대한 종단 간 지침을 제공합니다. 조직의 앱 스토어에서 사용자 지정 앱을 개발, 배포 및 관리하는 방법을 간소화하기 위해 Teams에서 앱 수명 주기 전체에서 제공하는 연결된 환경을 간단히 살짝 다루게 됩니다.

개발자가 Teams 앱 제출 API를 사용하여 사용자 지정 앱을 검토하고 승인할 수 있도록 사용자 지정 앱을 Microsoft Teams 관리 센터에 직접 제출하는 방법, 조직의 사용자에 대한 앱을 관리하기 위한 정책을 설정하는 방법, 사용자가 Teams에서 사용자가 검색하는 방법 등을 비롯해 수명 주기의 각 단계에 대해 다루지 않습니다.

![개발부터 배포로 앱 개요](media/custom-app-lifecycle.png)

이 지침은 앱의 Teams 통한 정보에 중점을 두고 관리자와 IT 전문가를 위한 것입니다. Teams 앱 개발에 관한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams 개발자 문서를 참조하세요.</a>

## <a name="develop"></a>개발

### <a name="create-the-app"></a>앱 만들기

Microsoft Teams 개발자 플랫폼은 개발자가 손쉽게 생산성을 향상하고 결정을 나누고 기존 콘텐츠 및 워크플로 에디션으로 공동 작업을 바인더로 만들 수 있습니다. Teams 플랫폼으로 구성된 앱은 Teams 클라이언트와 워크플로 간의 시각적 개체로, 공동 작업 플랫폼의 상황에 직접 액세스할 수 있습니다. 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams 개발자 설명서를 참조하세요.</a>

### <a name="submit-the-app"></a>앱 제출

앱이 프로모션에서 사용할 준비가 되면 개발자는 Teams 앱 제출 API를 사용하여 앱을 제출할 수 있습니다. 이러한 앱은 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Graph API,</a>Visual Studio 코드 등의 통합된 개발 환경(IDE), Power Apps 및 Power Rirtual Agents 같은 플랫폼에서 호출될 수 있습니다. 이렇게 하면 관리자가 앱을 검토하고 승인할 수 있습니다. <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> 

<a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph를</a>기으로 하는 Teams 앱 제출 API를 사용하면 조직에서 사용자가 선택한 플랫폼에서 개발하고 Teams에서 사용자 지정 앱에 대한 제출 방법을 자동화할 수 있습니다.

이 앱 제출 단계는 코드에 표시된 모양의 Visual Studio 예입니다.

![코드에서 앱을 Visual Studio 스크린샷](media/custom-app-lifecycle-submit-app.png)

조직의 앱 스토어에 앱이 아주 게시되지는 않습니다. 이 단계에서는 조직의 앱 스토어에 게시하기 위한 승인된 Microsoft Teams 관리 센터에 앱을 제출합니다.

Graph API를 사용하여 앱 제출에 대한 자세한 내용은 여기를 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">참조하세요.</a>

## <a name="validate"></a>Validate

Microsoft Teams <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">관리</a> 센터의 앱 관리 페이지(왼쪽 탐색 창에서 **Teams**앱  >  **관리**앱로 이동)에서 조직의 모든 Teams 앱을 볼 수 있습니다. 페이지 **맨 위에 있는 승인 보류** 중 위젯을 통해 사용자 지정 앱이 승인을 받기 위한 제출되는 시기를 알려줄 수 있습니다.

표에서 새로 제출된 앱에는 제출된 **게시** 및 차단됨 **상태의** 게시 **상태가** **자동으로 표시됩니다.** 게시 상태 열을 **내림차순으로** 정렬하여 앱을 빠르게 찾을 수 있습니다.

![보류 요청 및 앱 상태가 표시된 앱 관리 페이지 스크린샷 ](media/custom-app-lifecycle-validate-app.png)

앱 이름을 클릭하여 앱 세부 정보 페이지로 이동합니다. 정보 **탭에서** 설명, 상태, 제출자 및 앱 ID를 포함하여 앱에 대한 세부 정보를 볼 수 있습니다.

![제출된 앱에 대한 앱 세부 정보 페이지 스크린샷](media/custom-app-lifecycle-app-details.png)

Graph API를 사용하여 게시 상태를 확인하는 방법에 대한 **자세한 내용은 여기를** <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">참조하세요.</a>

## <a name="publish"></a>게시

사용자가 앱을 사용할 수 있도록 준비가 되면 앱을 게시합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 Teams 앱 관리 **앱으로**  >  **이동합니다.**
2. 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 게시 상태 **상자에서 게시를** **선택합니다.**

    앱을 게시하면 게시 상태가 **게시됨으로** **변경되며** **상태가 자동으로 허용됨으로** **변경됩니다.**

## <a name="set-up-and-manage"></a>설정 및 관리

### <a name="control-access-to-the-app"></a>앱에 대한 액세스 제어

기본적으로 조직의 모든 사용자는 조직의 앱 스토어에 있는 앱에 액세스할 수 있습니다. 앱을 사용할 권한이 있는 사용자를 제한하고 제어하려면 앱 사용 권한 정책을 만들어 할당하면 됩니다. 자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Teams에서 앱 사용 권한 정책 관리를 참조하세요.</a>

### <a name="pin-and-install-the-app-for-users-to-discover"></a>사용자가 검색할 앱을 고정 및 설치

기본적으로 사용자는 조직의 앱 스토어로 이동하여 검색하거나 검색해야 하는 앱을 찾을 수 있습니다. 사용자가 쉽게 앱에 액세스할 수 있도록 앱을 Teams의 앱 바에 고정할 수 있습니다. 이렇게 하려면 앱 설정 정책을 만들어 사용자에게 할당합니다. 자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Teams에서 앱 설치 정책 관리를 참조하세요.</a>

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams 앱 이벤트에 대한 감사 로그 검색

감사 로그를 검색하여 조직에서 Teams 앱 활동을 볼 수 있습니다. 감사 로그를 검색하고 감사 로그에 기록된 Teams 활동 목록을 보는 방법에 대한 자세한 내용은 Teams에서 이벤트에 대한 감사 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">로그 검색을 참조하세요.</a>

감사 로그를 검색하려면 먼저 보안 기능 및 준수 <a href="https://protection.office.com" target="_blank">센터에서 감사를 & 켜야 합니다.</a> 자세한 내용은 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">감사 로그 검색 켜기 또는 끄기를 참조하세요.</a> 감사 데이터는 감사를 설정한 지점부터만 사용할 수 있다는 점에 유의하세요.

## <a name="discover-and-adopt"></a>검색 및 실행

앱에 대한 권한이 있는 사용자는 조직의 앱 스토어에서 해당 앱을 찾을 수 있습니다. 앱 **페이지에 대한 기본 *제공로 이동하여* ** 조직의 사용자 지정 앱을 찾습니다.

![게시된 앱을 보여 주는 앱 페이지 스크린샷 ](media/custom-app-lifecycle-discovery.png)

앱 설정 정책을 만들고 할당한 경우 앱이 Teams의 앱 바에 고정되어 정책이 할당된 사용자가 쉽게 액세스할 수 있습니다.

## <a name="update"></a>업데이트

앱을 업데이트하려면 개발자가 개발 섹션의 단계를 계속 따를 [수](#develop) 있습니다.

개발자가 게시된 사용자 지정 앱에 업데이트를 제출하면 앱 관리 페이지의 **승인** 위젯에 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">알림이 표시됩니다.</a> 표에서 **앱의 게시 상태가** 제출됨으로 **설정됩니다.**

![보류 요청 및 앱 상태가 표시된 앱 관리 페이지 스크린샷 ](media/custom-app-lifecycle-update-submitted.png)

앱 업데이트를 검토하고 게시하려면:

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 Teams 앱 관리 **앱으로**  >  **이동합니다.**
2. 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 업데이트 **사용 가능을** 선택하여 업데이트 세부 사항을 검토합니다.

    ![보류 요청 및 앱 상태가 표시된 앱 관리 페이지 스크린샷 ](media/custom-app-lifecycle-update-app.png)
3. 준비가 되면 게시를 선택하여 **업데이트를** 게시합니다. 이렇게 하면 기존 앱이 대체되어 버전 번호가 업데이트되며 게시 **상태가 게시됨으로** **변경됩니다.** 업데이트된 앱에 대해 모든 앱 사용 권한 정책 및 앱 설정 정책이 그대로 유지됩니다.

    업데이트를 거절하는 경우 이전 버전의 앱은 게시된 상태로 유지됩니다.

다음 사항에 유의하세요.

- 앱이 승인되면 다른 사람은 모든 사용자가 앱에 대한 업데이트를 제출할 수 있습니다. 즉, 원래 앱을 제출한 개발자를 포함한 다른 개발자가 앱에 대한 업데이트를 제출할 수 있습니다.
- 개발자가 앱을 제출하고 요청이 보류 중이면 동일한 개발자만 앱에 대한 업데이트를 제출할 수 있습니다. 다른 개발자는 앱이 승인된 후에만 업데이트를 제출할 수 있습니다.

Graph API를 사용하여 앱을 업데이트하는 방법에 대한 자세한 내용은 여기를 <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">참조하세요.</a>

### <a name="update-experience-for-users"></a>사용자를 위한 업데이트 환경

대부분의 경우 앱 업데이트를 퍼블리싱하고 나면 사용자에게 새 버전이 자동으로 나타납니다. 그러나 사용자가 수락을 완료해야 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">하는 Microsoft Teams</a> 매니페스트에 몇 가지 업데이트가 있습니다.

* 부품이 추가 또는 제거되었습니다.
* 기존 의 "botId" 속성이 변경된 경우
* 기존 의 "isNotificationOnly" 속성이 변경된 경우
* 부트의 "supportsFiles" 속성이 변경됨
* 메시지 확장 기능이 추가 또는 제거되었습니다.
* 새 커넥터가 추가됨
* 새 정적 탭이 추가됨
* 새 구성 할 수 있는 탭이 추가됨
* "webApplicationInfo" 내의 속성이 변경됨

![사용할 수 있는 새 버전이 있는 앱을 보여 주는 스크린샷](media/manage-your-custom-apps-update1.png)

![앱 업그레이드 옵션 스크린샷](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>관련 항목

- [앱 패키지를 업로드하여 사용자 지정 앱 게시](upload-custom-apps.md)
- [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
- [Teams에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
- [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Teams 앱용 Microsoft Graph API</a>
