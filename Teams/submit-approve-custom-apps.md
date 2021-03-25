---
title: Teams App Submit API를 사용하여 사용자 지정 앱을 제출하고 승인합니다.
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams의 Teams 앱 제출 API를 사용하여 제출된 사용자 지정 앱을 승인하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 8c12d93a0b4420fd248064c69308e8049dc6326f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116976"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Teams 앱 제출 API를 통해 제출된 사용자 지정 앱 게시

## <a name="overview"></a>개요

> [!NOTE]
> 사용자 지정 Teams 앱을 게시할 때 조직의 앱 스토어의 사용자가 사용할 수 있습니다. 사용자 지정 앱을 게시하는 방법에는 두 가지가 있으며, 사용하는 방식은 앱을 다운로드하는 방법에 따라 다를 수 있습니다. 이 문서에서는 개발자가 Teams App Submit API 를 통해 제출하는 사용자 지정 앱을 승인하고 게시하는 방법에 **대해 중점적으로 다를 수 있습니다.** 사용자 지정 앱을 업로드하는 다른 방법은 개발자가 .zip 형식으로 앱 패키지를 보낼 때 사용됩니다. 해당 방법에 대한 자세한 내용은 앱 패키지를 업로드하여 사용자 지정 <a href="/microsoftteams/upload-custom-apps" target="_blank">앱 게시를 참조하세요.</a> 승인 앱 위젯은 GCC 테넌트에서 사용할 수 없습니다. 

> [!IMPORTANT]
> 이 메서드는 현재 GCC 환경에 사용할 수 없습니다. 사용자 지정 앱 업로드 *방법을 사용해야* 합니다.

이 문서에서는 Teams 앱을 개발에서 배포로 검색하는 방법에 대한 종단-종단 지침이 제공됩니다. Teams가 앱 수명 주기 전반에 걸쳐 제공하는 연결된 환경의 개요를 통해 조직의 앱 스토어에서 사용자 지정 앱을 개발, 배포 및 관리하는 방법을 간소화합니다.

개발자가 Teams App Submit API를 사용하여 사용자 지정 앱을 제출하여 검토하고 승인할 수 있도록 Microsoft Teams 관리 센터에 직접 제출하는 방법, 조직의 사용자에 대한 앱을 관리하기 위한 정책을 설정하는 방법, 사용자가 Teams에서 앱을 검색하는 방법을 포함하여 수명 주기의 각 단계를 다 덮습니다.

![개발에서 배포까지 앱 개요](media/custom-app-lifecycle.png)

이 지침은 앱의 Teams 측면에 중점을 두며 관리자 및 IT 프로를 위한 것입니다. Teams 앱 개발에 대한 자세한 내용은 Teams 개발자 설명서 <a href="/microsoftteams/platform" target="_blank">를 참조하세요.</a>

## <a name="develop"></a>개발

### <a name="create-the-app"></a>앱 만들기

Microsoft Teams 개발자 플랫폼을 사용하면 개발자가 사용자만의 앱 및 서비스를 통합하여 생산성을 향상하고, 의사 결정을 빠르게 내릴 수 있으며, 기존 콘텐츠 및 워크플로에 대한 공동 작업을 쉽게 만들 수 있습니다. Teams 플랫폼에 구축된 앱은 Teams 클라이언트와 서비스 및 워크플로 간의 브리지로, 공동 작업 플랫폼의 컨텍스트로 바로 연결됩니다. 자세한 내용은 Teams 개발자 설명서 <a href="/microsoftteams/platform" target="_blank">를 참조하세요.</a>

### <a name="submit-the-app"></a>앱 제출

앱이 프로덕션 환경에서 사용할 준비가 된 경우 개발자는 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API,</a>IDE(통합 개발 환경(예: IDE Visual Studio) 또는 Power Apps 및 Power Virtual Agents와 같은 플랫폼에서 호출할 수 있는 Teams App Submit API를 사용하여 앱을 제출할 수 있습니다. 이렇게 하면 Microsoft Teams <a href="/microsoftteams/manage-apps" target="_blank"></a> 관리 센터의 앱 관리 페이지에서 앱을 사용할 수 있으며, 여기서 관리자인 사용자가 앱을 검토하고 승인할 수 있습니다.

Microsoft Graph에 기반한 <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Teams</a>App 제출 API를 사용하면 조직에서 선택한 플랫폼에서 개발할 수 있으며 Teams의 사용자 지정 앱에 대한 제출-승인 프로세스를 자동화할 수 있습니다.

다음은 코드에서 이 앱 제출 단계의 모양을 Visual Studio 예입니다.

![코드에서 앱 Visual Studio 제출](media/custom-app-lifecycle-submit-app.png)

아직 조직의 앱 스토어에 앱을 게시하지 않습니다. 이 단계에서는 조직의 앱 스토어에 게시하기 위해 승인할 수 있는 Microsoft Teams 관리 센터에 앱을 제출합니다.

Graph API를 사용하여 앱을 제출하는 데 대한 자세한 내용은 여기를 <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">참조하세요.</a>

## <a name="validate"></a>유효성 검사

Microsoft <a href="/microsoftteams/manage-apps" target="_blank">Teams</a> 관리 센터의 앱 관리 페이지(왼쪽 탐색에서 **Teams Apps** 관리 앱으로 이동) 조직의 모든 Teams 앱에 대한 보기를  >  제공합니다. 페이지 **맨** 위에 있는 보류 중인 승인 위젯을 통해 사용자 지정 앱이 승인을 위해 제출된 경우를 알 수 있습니다.

표에서 새로 제출된 앱은 자동으로  제출 및 차단  상태의 게시 상태를 **보여 집니다.**  게시 상태  열을 내선 순서로 정렬하여 앱을 빠르게 찾을 수 있습니다.

![게시 상태 ](media/custom-app-lifecycle-validate-app.png)

앱 이름을 클릭하여 앱 세부 정보 페이지로 이동합니다. 정보 **탭에서** 설명, 상태, 제출자 및 앱 ID를 포함하여 앱에 대한 세부 정보를 볼 수 있습니다.

![제출된 앱에 대한 앱 세부 정보 페이지](media/custom-app-lifecycle-app-details.png)

Graph API를 사용하여 게시 상태를 확인한 자세한 내용은 **여기를** <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">참조하세요.</a>

## <a name="publish"></a>게시

사용자가 앱을 사용할 수 있도록 만들 준비가 되면 앱을 게시합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 게시 상태 **상자에서** 게시를 **선택합니다.**

    앱을 게시한 후  게시 상태가 **게시로** 변경되고  상태가 자동으로 허용 으로 **변경됩니다.**

## <a name="set-up-and-manage"></a>설정 및 관리

### <a name="control-access-to-the-app"></a>앱에 대한 액세스 제어

기본적으로 조직의 모든 사용자는 조직의 앱 스토어에서 앱에 액세스할 수 있습니다. 앱을 사용할 권한이 있는 사용자에 대한 제한 및 제어를 위해 앱 사용 권한 정책을 만들고 할당할 수 있습니다. 자세한 내용은 Teams 에서 <a href="/microsoftteams/teams-app-permission-policies" target="_blank">앱 사용 권한 정책 관리</a>를 참조하세요.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>사용자가 검색할 앱 고정 및 설치

기본적으로 사용자가 조직의 앱 스토어로 이동하여 찾아보거나 검색해야 하는 앱을 찾으면 됩니다. 사용자가 앱에 쉽게 도착할 수 있도록 Teams의 앱 표시줄에 앱을 고정할 수 있습니다. 이렇게하려면 앱 설정 정책을 만들고 사용자에게 할당합니다. 자세한 내용은 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Teams에서 앱 설정 정책 관리</a>를 참조하세요.

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams 앱 이벤트에 대한 감사 로그 검색

감사 로그를 검색하여 조직의 Teams 앱 활동을 볼 수 있습니다. 감사 로그를 검색하고 감사 로그에 기록된 Teams 활동 목록을 보는 방법에 대한 자세한 내용은 Teams의 이벤트에 대한 감사 로그 검색을 <a href="/microsoftteams/audit-log-events" target="_blank">참조하세요.</a>

감사 로그를 검색하려면 먼저 <a href="https://protection.office.com" target="_blank">보안 및 준수 센터</a>에서 감사를 켜야 합니다. 자세한 내용은 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">감사 로그 검색 설정 및 해제</a>를 참조하세요. 감사 데이터는 감사가 켜진 시점부터만 사용할 수 있습니다.

## <a name="discover-and-adopt"></a>검색 및 채택

앱에 대한 권한이 있는 사용자는 조직의 앱 스토어에서 찾을 수 있습니다. 앱 **페이지에서** 조직 이름에 대한 기본 제공 페이지로 이동하여 조직의 사용자 지정 앱을 찾으십시오.

![게시된 앱을 보여주는 앱 페이지 ](media/custom-app-lifecycle-discovery.png)

앱 설치 정책을 만들어 할당한 경우 앱이 Teams의 앱 표시줄에 고정되어 정책을 할당한 사용자에게 쉽게 액세스할 수 있습니다.

## <a name="update"></a>업데이트

앱을 업데이트하기 위해 개발자는 개발 섹션의 단계를 계속 [따라야](#develop) 합니다.

개발자가 게시된 사용자 지정 앱에 대한 업데이트를 제출하면 앱  관리 페이지의 승인 보류 중 위젯에서 <a href="/microsoftteams/manage-apps" target="_blank">알림을 받을 수</a> 있습니다. 표에서 앱의  게시 상태는 제출된 **업데이트로 설정됩니다.**

![보류 중인 요청 및 앱 상태를 표시하는 앱 페이지 관리 ](media/custom-app-lifecycle-update-submitted.png)

앱 업데이트를 검토하고 게시하는 경우:

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 사용 가능한 업데이트를 선택하여 업데이트 세부 정보를 검토합니다. 

    ![앱 세부 정보 페이지](media/custom-app-lifecycle-update-app.png)
3. 준비가되면 게시를 **선택하여** 업데이트를 게시합니다. 이렇게 하면 기존 앱이 바뀌고 버전 번호를 업데이트하고 게시 상태를 게시 **으로** **변경합니다.** 모든 앱 사용 권한 정책 및 앱 설정 정책은 업데이트된 앱에 대해 계속 적용됩니다.

    업데이트를 거부하면 이전 버전의 앱이 게시된 상태로 남아 있습니다.

다음을 염두에 두어야 합니다.

- 앱이 승인되면 모든 사용자가 앱에 업데이트를 제출할 수 있습니다. 즉, 앱을 처음 제출한 개발자를 포함하여 다른 개발자가 앱에 업데이트를 제출할 수 있습니다.
- 개발자가 앱을 제출하고 요청이 보류 중인 경우 동일한 개발자만 앱에 업데이트를 제출할 수 있습니다. 다른 개발자는 앱이 승인된 후에만 업데이트를 제출할 수 있습니다.

Graph API를 사용하여 앱을 업데이트하는 데 대한 자세한 내용은 여기를 <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">참조하세요.</a>

### <a name="update-experience-for-users"></a>사용자에 대한 환경 업데이트

대부분의 경우 앱 업데이트를 게시한 후 사용자에게 새 버전이 자동으로 나타납니다. 그러나 사용자 동의를 완료해야 하는 <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> 매니페스트에 대한 몇 가지 업데이트가 있습니다.

* 봇이 추가되거나 제거되었습니다.
* 기존 봇의 "botId" 속성이 변경된 경우
* 기존 봇의 "isNotificationOnly" 속성이 변경된 경우
* 봇의 "supportsFiles" 속성이 변경된 경우
* 메시징 확장이 추가되거나 제거되었습니다.
* 새 커넥터가 추가되었습니다.
* 새 정적 탭이 추가되었습니다.
* 새 구성 가능한 탭이 추가되었습니다.
* "webApplicationInfo" 내부 속성이 변경되었습니다.

![새 버전 사용 가능](media/manage-your-custom-apps-update1.png)

![앱의 업그레이드 옵션](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>관련 항목

- [앱 패키지를 업로드하여 사용자 지정 앱 게시](upload-custom-apps.md)
- [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
- [Teams에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
- [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
- <a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Teams용 Microsoft Graph API 앱</a>